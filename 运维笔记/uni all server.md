### uni-all-server

```
server.port=8080
management.server.port=8443

{% if eureka_client_enabled==true %}
eureka.client.enabled=true
eureka.client.serviceUrl.defaultZone=$${eureka_client_service_url_default_zone}
eureka.instance.hostname=$${eureka_instance_hostname}
eureka.instance.ip-address=$${eureka_instance_ip_address}
eureka.instance.non-secure-port=$${eureka_instance_non_secure_port}
eureka.instance.prefer-ip-address=true
spring.application.name=uni-all-web
{% else %}heading.uni.server.url=$${uni_url}
eureka.client.enabled=false
{% endif %}
```