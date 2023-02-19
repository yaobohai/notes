## 安装vsftpd

```
yum -y install vsftpd
yum -y install ftp
```

### 禁止匿名登录

```
CONFIG="/etc/vsftpd/vsftpd.conf"
sed -i '/^anonymous_enable/s/YES/NO/g' $CONFIG
```

### 允许本地用户登录
```
sed -i '/^local_enable/s/NO/YES/g' $CONFIG
sed -i '/^listen/s/NO/YES/g' $CONFIG
sed -i '/^listen_ipv6/s/YES/NO/g' $CONFIG
sed -i '/^userlist_enable/s/YES/NO/g' $CONFIG
```

### 添加本地登录用户用作ftp

```
USERS="/etc/vsftpd/user_list"
rm -rf $USERS
touch $USERS
useradd bohai
echo "bohai123." >passwd.txt
passwd  --stdin bohai < passwd.txt &>/dev/null
echo "bohai" >$USERS
rm -rf passwd.txt
```

###  启动ftp
systemctl start vsftpd
