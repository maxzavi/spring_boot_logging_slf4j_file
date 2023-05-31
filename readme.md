# Spring Boot - Slf4j Logger File Appender

Create Spring Boot project, with starters:
- **Lombok** Developer Tools

Config logging in application.yml

```yml
logging:
  level:
    root: INFO
  pattern:
    console: "%d{HH:mm:ss.SSS} [%t] %-5level %logger{36} - %msg%n"
    file: "%d %p %c{1.} [%t] %m%n"
  file:
    name: app.log
```
Implements **CommandLineRunner** for console application

```java
@SpringBootApplication
public class DemologfileApplication implements CommandLineRunner {
```

Use annotation **@Slf4j** in class, for loggig use **log.**

```java
@Slf4j
public class DemologfileApplication implements CommandLineRunner {

	public static void main(String[] args) {
		SpringApplication.run(DemologfileApplication.class, args);
	}

	@Override
	public void run(String... args) throws Exception {
		log.info("Start");
		log.info("End");
	}

}
```