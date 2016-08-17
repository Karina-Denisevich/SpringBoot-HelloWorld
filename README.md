# SpringBoot-HelloWorld

First I set up a basic build script [build.gradle](https://github.com/Karina-Denisevich/SpringBoot-HelloWorld/blob/master/build.gradle).

```java
repositories {
    mavenCentral()
}
```
The repositories block indicates that the build should resolve its dependencies from the Maven Central repository.</br>

```java
dependencies {
    compile('org.springframework.boot:spring-boot-starter-web')
    testCompile("junit:junit")
}
```
With the dependencies block, I declare the dependencies.<br>
Compile dependency, indicating that it should be available during compile-time.<br>
TestCompile dependencies used for compiling and running tests, but not required for building or running the project’s runtime code.<br>

___

Creating a web controller for the application [HelloController.java](https://github.com/Karina-Denisevich/SpringBoot-HelloWorld/blob/master/src/main/java/com/github/Karina_Denisevich/spring/boot/example/hello/HelloController.java).
```java
@RestController
public class HelloController {

    @RequestMapping("/")
    public String index() {

        return "Hello World!";
    }
}
```
The class is flagged as a @RestController, meaning it’s ready for use by Spring MVC to handle web requests. @RequestMapping maps / to the index() method. When invoked from a browser or using curl on the command line, the method returns pure text.<br>

___

[Application.java](https://github.com/Karina-Denisevich/SpringBoot-HelloWorld/blob/master/src/main/java/com/github/Karina_Denisevich/spring/boot/example/hello/Application.java) class with the components.
```java
@SpringBootApplication
public class Application {

    public static void main(String[] args) {

        ApplicationContext ctx = SpringApplication.run(Application.class, args);
    }
}
```
@SpringBootApplication is a convenience annotation that adds all of the following:

@Configuration tags the class as a source of bean definitions for the application context.

@EnableAutoConfiguration tells Spring Boot to start adding beans based on classpath settings, other beans, and various property settings.

Normally you would add @EnableWebMvc for a Spring MVC app, but Spring Boot adds it automatically when it sees spring-webmvc on the classpath. This flags the application as a web application and activates key behaviors such as setting up a DispatcherServlet.

@ComponentScan tells Spring to look for other components, configurations, and services in the the hello package, allowing it to find the HelloController.

___
