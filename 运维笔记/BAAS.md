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
```

