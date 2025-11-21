Demo of a Maven Micronaut Application which uses [NullAway](http://github.com/uber/NullAway). 

```
% sdk use java 21.0.9-graal
% ./mvnw verify    
[ERROR] COMPILATION ERROR : 
[INFO] -------------------------------------------------------------
[ERROR] /Users/sdelamo/github/sdelamo/micronaut-maven-nullaway-demo/src/main/java/example/micronaut/GreetingController.java:[21,39] [NullAway] dereferenced expression greetingService.greet() is @Nullable
    (see http://t.uber.com/nullaway )
[INFO] 1 error
[INFO] -------------------------------------------------------------
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  1.855 s
[INFO] Finished at: 2025-11-21T15:51:32+01:00
[INFO] ------------------------------------------------------------------------
[ERROR] Failed to execute goal org.apache.maven.plugins:maven-compiler-plugin:3.14.1:compile (default-compile) on project mn-maven-jspecify: Compilation failure
[ERROR] /Users/sdelamo/github/sdelamo/micronaut-maven-nullaway-demo/src/main/java/example/micronaut/GreetingController.java:[21,39] [NullAway] dereferenced expression greetingService.greet() is @Nullable
[ERROR]     (see http://t.uber.com/nullaway )
[ERROR] 
[ERROR] -> [Help 1]
```

- It defines the version of [NullAway](https://github.com/sdelamo/micronaut-maven-nullaway-demo/blob/main/pom.xml#L26)
- It defines the version of [Error Prone](https://github.com/sdelamo/micronaut-maven-nullaway-demo/blob/main/pom.xml#L25)
- It [adds the error prone annotation processor](https://github.com/sdelamo/micronaut-maven-nullaway-demo/blob/main/pom.xml#L103-L107)
- It [adds the null away annotation processor](https://github.com/sdelamo/micronaut-maven-nullaway-demo/blob/main/pom.xml#L108-L112)
- It [adds `.mvn/.jvmconfig` file](https://github.com/sdelamo/micronaut-maven-nullaway-demo/blob/main/.mvn/jvm.config) as [described in the error prone Maven documentation](https://errorprone.info/docs/installation#maven)
- [It adds `compilerArgs` for error prone and null away](https://github.com/sdelamo/micronaut-maven-nullaway-demo/blob/main/pom.xml#L96-L98)

