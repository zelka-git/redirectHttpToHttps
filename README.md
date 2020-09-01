# Spring Boot SSL [https] Example
In this spring boot example, learn to configure web application to run on SSL (HTTPS) with self-signed certificate. Also learn to create SSL cert, as well.

# SSL Configuration for Impatients
## Spring boot HTTPS Config
* server.port=8443
* server.ssl.key-alias=selfsigned_localhost_sslserver
* server.ssl.key-password=changeit
* server.ssl.key-store=classpath:ssl-server.jks
* server.ssl.key-store-provider=SUN
* server.ssl.key-store-type=JKS
## Redirect from HTTP to HTTPS
```
private Connector redirectConnector() {
  Connector connector = new Connector("org.apache.coyote.http11.Http11NioProtocol");
  connector.setScheme("http");
  connector.setPort(8080);
  connector.setSecure(false);
  connector.setRedirectPort(8443);
  return connector;
 }
 ```
[https://howtodoinjava.com/spring-boot/spring-boot-ssl-https-example](https://howtodoinjava.com/spring-boot/spring-boot-ssl-https-example/#:~:text=Redirect%20HTTP%20requests%20to%20HTTPS&text=To%20do%20that%20in%20spring,need%20to%20add%20below%20configuration.) - ref
