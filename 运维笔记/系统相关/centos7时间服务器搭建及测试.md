
# centos7时间服务器搭建及测试

## 时间，时区设定
查看当前系统日期和时间：  date

```
[root@ops-k8s-sh-master-01 ~]#  date
Wed Feb  1 09:35:46 CST 2023

# 在中国时区是CST，如果显示时区不正确，修改：tzselect        (time  zone)输入数字选择
[root@ops-k8s-sh-master-01 ~]#  timedatectl |grep "Time zone"
       Time zone: Asia/Shanghai (CST, +0800)
```

如若时区不对，需将时区信息拷贝，覆盖原来的时区信息

```
cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
```

搭建ntp时间服务器

```
[root@ops-k8s-sh-master-01 ~]# yum install ntp ntpdate -y 
[root@ops-k8s-sh-master-01 ~]#  cat /etc/ntp.conf |awk '{if($0 !~ /^$/ && $0 !~ /^#/) {print $0}}'
driftfile /var/lib/ntp/drift
logfile /var/log/ntpd.log
restrict default nomodify notrap nopeer noquery
restrict 0.0.0.0 mask 0.0.0.0 nomodify
#授权特定网段的主机可以从此时间服务器上查询和同步时间
restrict 127.0.0.1 
restrict ::1
server 0.cn.pool.ntp.org iburst
server 1.cn.pool.ntp.org iburst
server 2.cn.pool.ntp.org iburst
server 3.cn.pool.ntp.org iburst
server 192.168.150.201 iburst      #新增当外部时间不可用时可以使用本地时间
fudge 127.0.0.1 stratum 10   #startum为时间服务器的层次；设为0则为顶级，如果要向别的NTP服务器更新时间，请不要把它设为0，默认为10
includefile /etc/ntp/crypto/pw
keys /etc/ntp/keys
disable monitor

# 重启服务& 加入开机自启
systemctl restart ntpd
systemctl enable ntpd

#将当前时间和日期写入BIOS
echo "SYNC_HWCLOCK=yes" >> /etc/sysconfig/ntpd  
# 查看同步信息
[root@ops-k8s-sh-master-01 ~]#  ntpq -p
     remote           refid      st t when poll reach   delay   offset  jitter
==============================================================================
-119.28.183.184  100.122.36.196   2 u   84  128  277   44.321    3.351   1.163
+a.chl.la        131.188.3.222    2 u  129  128  377  194.889    0.265   7.473
*dns1.synet.edu. 202.118.1.47     2 u   56  128  377   37.266   -0.591   0.658
+stratum2-1.ntp. 194.190.168.1    2 u   74  128  377  113.911   -0.546  14.166
 ops-k8s-sh-mast .INIT.          16 u    - 1024    0    0.000    0.000   0.000
```


注释：

remote：即NTP主机的IP或主机名称；最左边的符号，“+”：代表目前正在作用钟的上层NTP；“*”：表示也有连上线，不过是作为次要联机的NTP主机。
refid：参考的上一层NTP主机的地址
st：即stratum阶层
when：几秒前曾做过时间同步更新的操作
poll：下次更新在几秒之后
reach：已经向上层NTP服务器要求更新的次数
delay：网络传输过程中延迟的时间
offset：时间补偿的结果
jitter：Linux系统时间与BIOS硬件时间的差异时间

Linux客户端

```
[root@slave2 ~]# yum install  ntpdate -y
[root@slave2 ~]# 
# 手动同步时间
[root@slave2 ~]# ntpdate  192.168.150.201
# 配置定时任务，同步时间
[root@slave2 ~]# crontab -e
# 每过半个小时同步一次
0 */30 * * * /usr/sbin/ntpdate -u cn.pool.ntp.org > /dev/null 2>&1; /sbin/hwclock -w

```

