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
