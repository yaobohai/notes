### uni-all-server

```
server.port=8080
management.server.port=8443
spring.datasource.url=jdbc:postgresql://$${datasource_pg_url}:$${datasource_pg_port}/$${datasource_pg_db}?reWriteBatchedInserts=true
spring.datasource.username=$${datasource_pg_username}
spring.datasource.password=$${datasource_pg_password}
spring.datasource.driver-class-name=org.postgresql.Driver
spring.datasource.dbcp2.validation-query=SELECT 1

eureka.client.enabled=false
spring.application.name=uni-all-server
```