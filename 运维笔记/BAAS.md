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

