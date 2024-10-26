## What is Spring Boot?
* Spring Boot provides a good platform for Java developers to develop a stand-alone and production-grade spring application that you can just run. You can get started with minimum configurations without the need for an entire Spring configuration setup.

### Dependencies:
1. @EnableAutoConfiguration
2. @SpringBootApplication
3. @ComponentScan

### Spring Boot Starters:
1. spring-boot-starter-data-jpa
2. spring-boot-starter-*

### example code:
```
<dependency>
   <groupId>org.springframework.boot</groupId>

   <artifactId>spring-boot-starter-actuator</artifactId>
//Spring Boot Starter Actuator dependency is used to monitor and manage your application.

   <artifactId>spring-boot-starter-security</artifactId>
//Spring Boot Starter Security dependency is used for Spring Security.

   <artifactId>spring-boot-starter-web</artifactId>
//Spring Boot Starter web dependency is used to write a Rest Endpoints.

   <artifactId>spring-boot-starter-thymeleaf</artifactId>
//Spring Boot Starter Thyme Leaf dependency is used to create a web application.

   <artifactId>spring-boot-starter-test</artifactId>
//Spring Boot Starter Test dependency is used for writing Test cases.

</dependency>
```
