this is bieminzhiyu mall config

custom.port: port

custom.eureka-server: eureka server url



| module                         | port | application-name | remark |
| ------------------------------ | ---- | ---------------- | ------ |
| beiminzhiyu-mall-config-server | 8081 | config-server    |        |
| beiminzhiyu-mall-eureka-server | 8082 | eureka-server    |        |
| beiminzhiyu-mall-member        | 8083 | member-service   |        |
| beiminzhiyu-mall-message       | 8084 | message-service  |        |
|                                |      |                  |        |

eureka client example:

```java
custom:
  port: 8082
  server: 192.168.31.204
  eureka-server: http://${custom.server}:8082/eureka
spring:
  cloud:
    config:
      uri: http://${custom.server}:8081/
      label: master
      profile: dev
      name: member-service
```

