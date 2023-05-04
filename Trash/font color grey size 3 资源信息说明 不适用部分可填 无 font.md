<font color="grey" size=3>资源信息说明，不适用部分可填「无」</font>

```
云厂商和区域：华为云-华北3(张家口) ？
是否托管： 否
资源组：「无」
iwms应用服务网关入口地址： https://wms.mkh.cn:9090/

域名列表：
- 前端登录：http://wms.mkh.cn:9091/
- 接口平台：iwms-apidocs.bailebaihuo.com
- 报表平台：iwms-report.bailebaihuo.com
- 网关地址：iwms-gw.bailebaihuo.com 

均由 明康汇 客户信息部通过waf发布至外网。
```

### iwms调用链路 

仅部署了iWMS组件   

```mermaid
flowchart LR

subgraph ECS
web(iwms-web <br> 10.151.0.151:80) -->gw(iwms-zuul <br> 10.151.0.151:9009)
apidocs(iwms-platform-web <br> 10.151.0.151:81) -->gw(iwms-zuul <br> 10.151.0.151:9009)
gw(iwms-zuul <br> 10.151.0.151:9009)-->eureka(iwms-eureka <br> 10.151.0.151:9009)
eureka(iwms-eureka <br> 10.151.0.151:8761)-->iwms(iwms-account * 2<br>iwms-basic * 2<br>openapi-server * 2<br>wms-server * 2) 

iwms(iwms-account * 2<br>iwms-basic * 2<br>openapi-server * 2<br>wms-server * 2) -->report(iwms-report <br> 10.151.0.34:8091) 
iwms(iwms-account * 2<br>iwms-basic * 2<br>openapi-server * 2<br>wms-server * 2) -->许可证(lickit-server <br> 10.151.0.151:9080)
end
 
gw(iwms-zuul <br> 10.151.0.151:9009)-.->redis[(Redis 5.0)]  

iwms(iwms-account * 2<br>iwms-basic * 2<br>openapi-server * 2<br>wms-server * 2) -.->mysql[(RDS MySQL 5.7)] 
iwms(iwms-account * 2<br>iwms-basic * 2<br>openapi-server * 2<br>wms-server * 2) -.->redis[(Redis 5.0)]
iwms(iwms-account * 2<br>iwms-basic * 2<br>openapi-server * 2<br>wms-server * 2) -.->rumba-oss[(rumba-oss)] 
 
rumba-oss(rumba-oss <br> 10.151.0.151:8071) -.-> OBS[(OBS <br> 通过mount方式)] 
report(iwms-report <br> 10.151.0.34:8091) -.->mysql[(RDS MySQL 5.7)] 


subgraph "WAF公网域名发布<br>"
  subgraph "网关服务<br>"
    https://wms.mkh.cn:9090/
  end
  subgraph "报表服务<br>"
    http://iwms-report.mkh.cn:8091/iwms-report/
  end
  subgraph "接口平台<br>"
    http://hd-api-plat.mkh.cn/config/
  end
  subgraph "前端服务<br>"
    http://wms.mkh.cn:9091/index.html/
  end

end

https://wms.mkh.cn:9090/ --> gw
http://iwms-report.mkh.cn:8091/iwms-report/ --> report
http://hd-api-plat.mkh.cn/config/ --> apidocs
http://wms.mkh.cn:9091/index.html/ --> web
```

需注意：通过上述接口图可看出，iWMS业务组件本身不支持华为云obs对象存储，通过mount方式将obs挂载至 `10.151.0.151` 并自建 `rumba-oss` 数据目录指向obs的挂载目录，完成对象存储数据存储。


### 机器及应用节点情况

<table>
    <tr>
        <td>ECS</td>
        <td>应用</td>
        <td>节点数</td>
    </tr>
    <tr>
        <td rowspan="5">10.151.0.151<br>4核16G</td>
        <td>lickit-server</td>
        <td>1</td>
    </tr>
    <tr>
        <td>iwms-eureka</td>
        <td>1</td>
    </tr>
    <tr>
        <td>iwms-zuul</td>
        <td>1</td>
    </tr>
    <tr>
        <td>iwms-web</td>
        <td>1</td>
    </tr>
    <tr>
        <td>iwms-platform-web</td>
        <td>1</td>
    </tr>
    <tr>
        <td rowspan="7">10.151.0.228<br>8核32G</td>
        <td>iwms-account</td>
        <td>1</td>
    </tr>
    <tr>
        <td>iwms-basic</td>
        <td>1</td>
    </tr>
    <tr>
        <td>openapi-server</td>
        <td>1</td>
    </tr>
    <tr>
        <td>wms-server</td>
        <td>1</td>
    </tr>
    <tr>
        <td rowspan="6">172.26.217.22<br>4核16G</td>
        <td>iwms-account</td>
        <td>1</td>
    </tr>
    <tr>
        <td>iwms-basic</td>
        <td>1</td>
    </tr>
    <tr>
        <td>openapi-server</td>
        <td>1</td>
    </tr>
    <tr>
        <td>wms-server</td>
        <td>1</td>
    </tr>
    <tr>
        <td>ips-archive</td>
        <td>1</td>
    </tr>
    <tr>
        <td>ips-bill</td>
        <td>1</td>
    </tr>
    <tr>
        <td rowspan="1">172.26.217.20<br>4核32G</td>
        <td>iwms-report</td>
        <td>1</td>
    </tr>
</table>
