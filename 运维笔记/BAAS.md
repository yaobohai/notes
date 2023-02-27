## BAAS

### config-service

```
// 运维配置
management.server.port=8443
server.port=8080
eureka.client.enabled=false
baas-config.dataSource.url=jdbc:mysql://$${datasource_url}:3306/baas?useUnicode=yes&characterEncoding=utf-8&useSSL=no
baas-config.dataSource.username=$${datasource_username}
baas-config.dataSource.password=$${datasource_password}

Xmx=
Xms=
Xmn=
Xml=
k8s.enabled=true
k8s.namespace=
```


### gateway-service

```
management.server.port=8443
management.endpoints.web.exposure.include=*
management.endpoint.env.enabled=false
management.endpoint.shutdown.enabled=true
management.endpoint.sessions.enabled=false
management.health.rabbit.enabled=false
management.server.port=8443
server.port=8080
server.tomcat.accesslog.pattern=%t %{trace_id}i %a %m %U %s %D %b %{User-Agent}i
server.tomcat.accesslog.enabled=True
server.tomcat.accesslog.prefix=localhost_access_log
server.tomcat.accesslog.suffix=.txt
server.tomcat.max-threads=1000
server.tomcat.accept-count=1000
eureka.client.enabled=false
spring.profiles.active=prd
spring.redis.host=
spring.redis.port=6379
spring.redis.database=
spring.redis.password=
logging.level.org.springframework.cloud.gateway.handler.predicate=ERROR
spring.cloud.gateway.discovery.locator.enabled=true
management.metrics.distribution.percentiles-histogram.http.server.requests=false
management.metrics.distribution.percentiles.http.server.requests=0.8,0.95,0.99

Xmx=
Xms=
Xmn=
Xml=
k8s.enabled=true
k8s.namespace=
```

### fms-service

```management.server.port=8443
server.port=8080
eureka.client.enabled=false
fms-service.dataSource.password=$${datasource_password}
fms-service.dataSource.url=jdbc:mysql://$${datasource_url}:3306/fms?useUnicode=yes&characterEncoding=utf-8&useSSL=no&serverTimezone=GMT%2B8
fms-service.dataSource.username=$${datasource_username}
fms-service.redis.host=$${redisIp}
fms-service.redis.port=$${redisPort}
fms-service.redis.password=$${redisPassword}
fms-service.redis.dbIndex=$${redisDb}
fms-service.es.enable=true
fms-service.es.url=$${es_url}
fms-service.es.username=$${es_username}
fms-service.es.password=$${es_password}
fms-service.es.keepDays=90

{% if rabbit_mns_mq==true %}fms-service.mns.mq=rabbitMQ
rumba-mq-amqp.user=hdmq
rumba-mq-amqp.passwd=dsagLu8myG6Mq
rumba-mq-amqp.host=$${mq_host}
rumba-mq-amqp.port=5672
rumba-mq-amqp.retry.delayTime=180000
management.health.rabbit.enabled=true{% endif %}
{% if rumba_mq_aliyun==true %}fms-service.mns.mq=aliyun
rumba-mq-aliyun.accessId=$${mns_accessKeyId}
rumba-mq-aliyun.secretKey=$${mns_accessKeySecret}
rumba-mq-aliyun.mnsEndpoint=$${mns_endpoint}{% endif %}
{% if rumba_mq_rocketMQ==true %}fms-service.mns.mq=rocketMQ
rumba-mq-rocketmq.accessChannel=CLOUD
rumba-mq-reliableevent.manager.name=R_MQRE
rumba-mq-rocketmq.accessKey=$${rocketmq_accesskey}
rumba-mq-rocketmq.secretKey=$${rocketmq_secretkey}
rumba-mq-rocketmq.instanceId=$${rocketmq_instanceId}
rumba-mq-rocketmq.producerGroup=baas
rumba-mq-rocketmq.regionId=$${rocketmq_regionId}
rumba-mq-rocketmq.nameSrvAddr=$${rocketmq_namesrvaddr}{% endif %}
{% if heading_uni_server==true %}heading.uni.server.url=$${heading_uni_server_url}
heading.uni.server.username=$${heading_uni_server_username}
heading.uni.server.password=$${heading_uni_server_password}
heading.uni.server.algorithm=RS256
websocket.authSource=uni
{% else %}websocket.authSource=tlsp
tlsp.url=$${tlsp_url}
tlsp.username=$${tlsp_rest_username}
tlsp.password=$${tlsp_rest_password}{% endif %}

Xmx=
Xms=
Xmn=
Xml=
k8s.enabled=true
k8s.namespace=
```

### spms-console-server

```
server.port=8080

spring.redis.database=
spring.redis.host=
spring.redis.port=6379
spring.redis.timeout=30000
spring.redis.password=
spring.sleuth.stream.enabled=false
spring.cloud.nacos.config.enabled=false
spring.cloud.consul.enabled=false
eureka.client.enabled=false
management.server.port=8443
management.endpoint.env.enabled=false
management.endpoint.shutdown.enabled=true
management.endpoint.sessions.enabled=false
spms-console-server.datasource.driver-class-name=com.mysql.jdbc.Driver
spms-console-server.datasource.url=jdbc:mysql://$${datasource_url}:3306/spms?
spms-console-server.datasource.username=
spms-console-server.datasource.password=
management.metrics.distribution.percentiles-histogram.http.server.requests=false
management.metrics.distribution.percentiles.http.server.requests=0.8,0.95,0.99

Xmx=
Xms=
Xmn=
Xml=
k8s.enabled=true
k8s.namespace=
```

### spms-sync-server

```
server.port=8080
spring.redis.database=
spring.redis.host=
spring.redis.port=6379
spring.redis.password=
spring.sleuth.stream.enabled=false
spring.cloud.nacos.config.enabled=false
eureka.client.enabled=false
management.server.port=8443
management.health.rabbit.enabled=false
management.endpoint.env.enabled=false
management.endpoint.shutdown.enabled=true
management.endpoint.sessions.enabled=false
spms-sync-server.datasource.driver-class-name=com.mysql.jdbc.Driver
spms-sync-server.datasource.url=jdbc:mysql://$${datasource_url}:3306/spms?
spms-sync-server.datasource.username=
spms-sync-server.datasource.password=
spms-sync-server.datasource.validation-query=values 1
management.metrics.distribution.percentiles-histogram.http.server.requests=false
management.metrics.distribution.percentiles.http.server.requests=0.8,0.95,0.99

Xmx=
Xms=
Xmn=
Xml=
k8s.enabled=true
k8s.namespace=
```


### spms-zlportal-web

```
server.port=8080
management.server.port=8443
spring.redis.database=$${redisDb}
spring.redis.host=$${redisIp}
spring.redis.port=$${redisPort}
spring.redis.password=$${redisPassword}
spring.redis.timeout=30000
eureka.client.enabled=false
spms-server.datasource.driver-class-name=com.mysql.jdbc.Driver
spms-server.datasource.url=jdbc:mysql://$${datasource_url}:3306/$${datasource_db}
spms-server.datasource.username=$${datasource_username}
spms-server.datasource.password=$${datasource_password}
spms-server.datasource.validation-query=values 1
{% if spms_web_oss_aliyun==true %}spms-web.oss=aliyun
rumba-oss-aliyun.bucketName=$${oss_bucket}
rumba-oss-aliyun.connection.accessKeyId=$${oss_accessKeyId}
rumba-oss-aliyun.connection.accessKeySecret=$${oss_accessKeySecret}
rumba-oss-aliyun.connection.endpoint=$${oss_accessAddress}
rumba-oss-aliyun.connection.securetyToken={% endif %}
```


### zl-app-service

```
server.port=8080
management.server.port=8443
spring.application.name=$${zl_app_spring_application_name}
eureka.client.enabled=false
{% if zl_app_service=="tenant" %}
zl-app-service.datasource.url=jdbc:mysql://$${datasource_url}:3306/$${datasource_db}?useUnicode=yes&characterEncoding=utf-8&useSSL=no&serverTimezone=Asia/Shanghai
{% else %}
zl-app-service.datasource.url=jdbc:mysql://$${datasource_url}:3306/zl-app?useUnicode=yes&characterEncoding=utf-8&useSSL=no&serverTimezone=Asia/Shanghai
{% endif %}
zl-app-service.datasource.username=$${datasource_username}
zl-app-service.datasource.password=$${datasource_password}
zl-app-service.redis.host=$${redisIp}
zl-app-service.redis.port=$${redisPort}
zl-app-service.redis.password=$${redisPassword}
zl-app-service.redis.database=$${redisDb}
{% if app_service_user=="lhjx" %}zl-app-service.user=lhjx
zl-app-service.oss.enabled=false
ots.endPoint=$${ots_endPoint}
ots.accessKeyId=$${ots_accessKeyId}
ots.accessKeySecret=$${ots_accessKeySecret}
ots.instanceName=$${ots_instanceName}
zl-app-service.mns.mq=rocketMQ
rumba-mq-rocketmq.accessChannel=CLOUD
rumba-mq-rocketmq.accessKey=$${rocketmq_accesskey}
rumba-mq-rocketmq.secretKey=$${rocketmq_secretkey}
rumba-mq-rocketmq.instanceId=$${rocketmq_instanceId}
rumba-mq-rocketmq.producerGroup=GID_R_SENFER
rumba-mq-rocketmq.regionId=$${rocketmq_regionId}
rumba-mq-rocketmq.nameSrvAddr=$${rocketmq_namesrvaddr}
zl-app-service.dft.serverUrl=$${dft_config_serverUrl}
zl-app-service.dft.tenant=$${dft_config_tenant}
zl-app-service.dft.username=$${dft_config_username}
zl-app-service.dft.password=$${dft_config_password}
zl-app-service.dft.httpMaxPerRoute=30
zl-app-service.dft.httpMaxPoolTotal=30
zl-app-service.dft.httpSocketTimeout=10000
zl-app-service.dft.httpConnectionTimeout=10000
zl-app-service.geersign.certPath=/opt/app/server.pfx
zl-app-service.geersign.certKey=$${zl_app_service_geersign_certKey}
zl-app-service.job.cleanExpiredPayCodeJob.enabled=true
zl-app-service.job.tranPayCodeConsumeRecordJob.enabled=false
zl-app-service.job.tranPayCodeConsumeRecordJob.cron=0 0 0 * * ?
zex.ribbon.ConnectTimeout=1000
zex.ribbon.ReadTimeout=2000
```


### zl-oas-pt-service

```
server.port=8080
management.server.port=8443
eureka.client.enabled=false
oas-pt.redis.host=$${redisIp}
oas-pt.redis.port=$${redisPort}
oas-pt.redis.password=$${redisPassword}
oas-pt.redis.dbIndex=$${redisDb}
oas-pt.dataSource.username=$${datasource_username}
oas-pt.dataSource.password=$${datasource_password}
oas-pt.dataSource.url=jdbc:mysql://$${datasource_url}:3306/oas-pt?useUnicode=yes&characterEncoding=utf-8&useSSL=no&serverTimezone=Asia/Shanghai
{% if rabbit_mns_mq==true %}oas-pt.mns.mq=rabbitMQ
rumba-mq-amqp.user=hdmq
rumba-mq-amqp.passwd=dsagLu8myG6Mq
rumba-mq-amqp.host=$${mq_host}
rumba-mq-amqp.port=5672
rumba-mq-amqp.retry.delayTime=180000
management.health.rabbit.enabled=true{% endif %}
{% if rumba_mq_aliyun==true %}oas-pt.mns.mq=aliyun
rumba-mq-aliyun.accessId=$${mns_accessKeyId}
rumba-mq-aliyun.secretKey=$${mns_accessKeySecret}
rumba-mq-aliyun.mnsEndpoint=$${mns_endpoint}
management.health.rabbit.enabled=false{% endif %}
{% if rumba_mq_rocketMQ==true %}oas-pt.mns.mq=rocketMQ
rumba-mq-rocketmq.accessChannel=CLOUD
rumba-mq-reliableevent.manager.name=R_MQRE
rumba-mq-rocketmq.accessKey=$${rocketmq_accesskey}
rumba-mq-rocketmq.secretKey=$${rocketmq_secretkey}
rumba-mq-rocketmq.instanceId=$${rocketmq_instanceId}
rumba-mq-rocketmq.producerGroup=baas
rumba-mq-rocketmq.regionId=$${rocketmq_regionId}
rumba-mq-rocketmq.nameSrvAddr=$${rocketmq_namesrvaddr}{% endif %}
oas-pt.ostore.prefix=$${mns_stuffix}
{% if rumba_oss_aliyun==true %}oas-pt.ostore.active=aliyun
oas-pt.oss.bucketName=$${bucketName}
oas-pt.oss.accessKeyId=$${oss_accessKeyId}
oas-pt.oss.accessKeySecret=$${oss_accessKeySecret}
oas-pt.oss.endpoint=$${ossEndpoint}
oas-pt.oss.roleArn=$${oss_roleArn}
oas-pt.oss.stsEndpoint=$${oss_stsEndpoint}{% endif %}
```


### zl-oas-pt-bff

```server.port=8080
management.server.port=8443
eureka.client.enabled=false
```


### zl-pas-service

```management.server.port=8443
server.port=8080
eureka.client.enabled=false
pas-service.dataSource.testOnBorrow=false
pas-service.dataSource.maxActive=1000
pas-service.dataSource.minIdle=500
pas-service.dataSource.initialSize=100
pas-service.dataSource.username=$${datasource_username}
pas-service.dataSource.password=$${datasource_password}
pas-service.dataSource.url=jdbc:mysql://$${datasource_url}:3306/pas?useUnicode=yes&characterEncoding=utf-8&useSSL=no&serverTimezone=GMT%2B8
```

### zl-sas-service

```
management.server.port=8443
server.port=8080
spring.application.name=$${dnet_stackId}
eureka.client.enabled=false
sas-service.dataSource.password=$${datasource_password}
sas-service.dataSource.url=jdbc:mysql://$${datasource_url}:3306/$${datasource_db}?useUnicode=yes&characterEncoding=utf-8&useSSL=no&serverTimezone=GMT%2B8
sas-service.dataSource.username=$${datasource_username}
sas-service.dataSource.testOnBorrow=false
sas-service.dataSource.maxActive=1000
sas-service.dataSource.minIdle=500
sas-service.dataSource.initialSize=100
{% if rabbit_mns_mq==true %}sas-service.mns.mq=rabbitMQ
rumba-mq-amqp.user=hdmq
rumba-mq-amqp.passwd=dsagLu8myG6Mq
rumba-mq-amqp.host=$${mq_host}
rumba-mq-amqp.port=5672
rumba-mq-amqp.retry.delayTime=180000
management.health.rabbit.enabled=true{% endif %}
{% if rumba_mq_aliyun==true %}sas-service.mns.mq=aliyun
rumba-mq-aliyun.accessId=$${mns_accessKeyId}
rumba-mq-aliyun.secretKey=$${mns_accessKeySecret}
rumba-mq-aliyun.mnsEndpoint=$${mns_endpoint}{% endif %}
{% if rumba_mq_rocketMQ==true %}sas-service.mns.mq=rocketMQ
rumba-mq-rocketmq.accessChannel=CLOUD
rumba-mq-reliableevent.manager.name=R_MQRE
rumba-mq-rocketmq.accessKey=$${rocketmq_accesskey}
rumba-mq-rocketmq.secretKey=$${rocketmq_secretkey}
rumba-mq-rocketmq.instanceId=$${rocketmq_instanceId}
rumba-mq-rocketmq.producerGroup=baas
rumba-mq-rocketmq.regionId=$${rocketmq_regionId}
rumba-mq-rocketmq.nameSrvAddr=$${rocketmq_namesrvaddr}{% endif %}
sas-service.redis.host=$${redisIp}
sas-service.redis.port=$${redisPort}
sas-service.redis.password=$${redisPassword}
sas-service.redis.dbIndex=$${redisDb}
sas-service.redis.global.host=$${sas_service_redis_global_redisIp}
sas-service.redis.global.port=6379
sas-service.redis.global.password=$${sas_service_redis_global_redisPassword}
sas-service.redis.global.dbIndex=$${sas_service_redis_global_dbIndex}
sas-service.redis.global.maxTotal=100
sas-service.redis.maxTotal=1000
sas-service.redis.global.maxIdle=100
sas-service.redis.maxIdle=100
sas-service.redis.global.minIdle=50
sas-service.redis.minIdle=50
{% if rumba_oss_aliyun==true %}sas-service.ostore.active=aliyun
sas-service.oss.endpoint=$${ossEndpoint}
sas-service.oss.bucketName=$${bucketName}
sas-service.oss.accessKeyId=$${oss_accessKeyId}
sas-service.oss.accessKeySecret=$${oss_accessKeySecret}
sas-service.oss.roleArn=$${oss_roleArn}
sas-service.oss.stsEndpoint=$${oss_stsEndpoint}
sas-service.oss.urlExpirationMinute=30{% endif %}
```


