Demo of a Maven Micronaut Application which uses [NullAway](http://github.com/uber/NullAway). 

- It defines the version of [NullAway](https://github.com/sdelamo/micronaut-maven-nullaway-demo/blob/main/pom.xml#L26)
- It defines the version of [Error Prone](https://github.com/sdelamo/micronaut-maven-nullaway-demo/blob/main/pom.xml#L25)
- It [adds the error prone annotation processor](https://github.com/sdelamo/micronaut-maven-nullaway-demo/blob/main/pom.xml#L103-L107)
- It [adds the null away annotation processor](https://github.com/sdelamo/micronaut-maven-nullaway-demo/blob/main/pom.xml#L108-L112)
- It [adds `.mvn/.jvmconfig` file](https://github.com/sdelamo/micronaut-maven-nullaway-demo/blob/main/.mvn/jvm.config) as [described in the error prone Maven documentation](https://errorprone.info/docs/installation#maven)
- [It adds `compilerArgs` for error prone and null away](https://github.com/sdelamo/micronaut-maven-nullaway-demo/blob/main/pom.xml#L96-L98)
