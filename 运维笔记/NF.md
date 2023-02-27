## NF

### nightfury-web-service

```
management.server.port=8443
server.port=8080
spring.application.name=$${nf_web_spring_application_name}eureka.client.enabled=false
spring.datasource.nightfury.url=jdbc:mysql://$${datasource_url}:$${datasource_port}/$${datasource_db}?characterEncoding=utf-8&zeroDateTimeBehavior=convertToNull&serverTimezone=GMT%2B8
spring.datasource.nightfury.username=$${datasource_username}
spring.datasource.nightfury.password=$${datasource_password}
spring.redis.database=$${redisDb}
spring.redis.host=$${redisIp}
spring.redis.port=$${redisPort}
spring.redis.password=$${redisPassword}
alibaba.cloud.oss.enabled=$${oss_enabled}
alibaba.cloud.oss.endpoint=$${ossEndpoint}
alibaba.cloud.oss.public-endpoint=$${ossimageBaseUrl}
alibaba.cloud.oss.bucket=$${bucketName}
alibaba.cloud.access-key=$${oss_accessKeyId}
alibaba.cloud.secret-key=$${oss_accessKeySecret}
{% if rabbit_mns_mq==true %}spms-service.mns.mq=rabbitMQ
rumba-mq-amqp.user=hdmq
rumba-mq-amqp.passwd=dsagLu8myG6Mq
rumba-mq-amqp.host=$${mq_host}
rumba-mq-amqp.port=5672{% endif %}
{% if rumba_mq_rocketMQ==true %}spms-service.mns.mq=rocketMQ
rumba-mq-rocketmq.accessChannel=CLOUD
rumba-mq-rocketmq.accessKey=$${rocketmq_accesskey}
rumba-mq-rocketmq.secretKey=$${rocketmq_secretkey}
rumba-mq-rocketmq.instanceId=$${rocketmq_instanceId}
rumba-mq-rocketmq.producerGroup=GID_R_SENFER
rumba-mq-rocketmq.regionId=$${rocketmq_regionId}
rumba-mq-rocketmq.nameSrvAddr=$${rocketmq_namesrvaddr}{% endif %}
{% if rumba_mq_aliyun==true %}spms-service.mns.mq=aliyun
rumba-mq-aliyun.accessId=$${mns_accessKeyId}
rumba-mq-aliyun.secretKey=$${mns_accessKeySecret}
rumba-mq-aliyun.mnsEndpoint=$${mns_endpoint}
management.health.rabbit.enabled=false{% endif %}
```


### nightfury-service

```
management.server.port=8443
server.port=8080
spring.application.name=$${nf_spring_application_name}eureka.client.enabled=false
spring.datasource.nightfury.url=jdbc:mysql://$${datasource_url}:$${datasource_port}/$${datasource_db}?characterEncoding=utf-8&zeroDateTimeBehavior=convertToNull&serverTimezone=GMT%2B8
spring.datasource.nightfury.username=$${datasource_username}
spring.datasource.nightfury.password=$${datasource_password}
spring.redis.database=$${redisDb}
spring.redis.host=$${redisIp}
spring.redis.port=$${redisPort}
spring.redis.password=$${redisPassword}
alibaba.cloud.oss.enabled=$${oss_enabled}
alibaba.cloud.oss.endpoint=$${ossEndpoint}
alibaba.cloud.oss.public-endpoint=$${ossimageBaseUrl}
alibaba.cloud.oss.bucket=$${bucketName}
alibaba.cloud.access-key=$${oss_accessKeyId}
alibaba.cloud.secret-key=$${oss_accessKeySecret}
{% if rabbit_mns_mq==true %}spms-service.mns.mq=rabbitMQ
rumba-mq-amqp.user=hdmq
rumba-mq-amqp.passwd=dsagLu8myG6Mq
rumba-mq-amqp.host=$${mq_host}
rumba-mq-amqp.port=5672{% endif %}
{% if rumba_mq_rocketMQ==true %}spms-service.mns.mq=rocketMQ
rumba-mq-rocketmq.accessChannel=CLOUD
rumba-mq-rocketmq.accessKey=$${rocketmq_accesskey}
rumba-mq-rocketmq.secretKey=$${rocketmq_secretkey}
rumba-mq-rocketmq.instanceId=$${rocketmq_instanceId}
rumba-mq-rocketmq.producerGroup=GID_R_SENFER
rumba-mq-rocketmq.regionId=$${rocketmq_regionId}
rumba-mq-rocketmq.nameSrvAddr=$${rocketmq_namesrvaddr}{% endif %}
{% if rumba_mq_aliyun==true %}spms-service.mns.mq=aliyun
rumba-mq-aliyun.accessId=$${mns_accessKeyId}
rumba-mq-aliyun.secretKey=$${mns_accessKeySecret}
rumba-mq-aliyun.mnsEndpoint=$${mns_endpoint}
management.health.rabbit.enabled=false{% endif %}

```
