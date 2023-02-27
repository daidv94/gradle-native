# Spring Boot Native Image Microservice Example

This demo shows how to build, package, and run a simple Spring Boot 3 microservice from a JAR file with the GraalVM JDK, and from a native executable with GraalVM Native Image.
The benefits of using a native executable are much smaller size, faster start-up times, and reduced memory consumption.
It also demonstrates how to run the application and build the native executable within a Docker container.

There are two ways to generate a native executable from a Spring Boot application:

- [Using Buildpacks](https://docs.spring.io/spring-boot/docs/3.0.0/reference/html/native-image.html#native-image.developing-your-first-application.buildpacks)
- [Using GraalVM Native Build Tools](https://docs.spring.io/spring-boot/docs/3.0.0/reference/html/native-image.html#native-image.developing-your-first-application.native-build-tools)

## Preparation

1. Download and install GraalVM JDK from guildline in homepage [GraalVM Install](https://www.graalvm.org/latest/docs/getting-started/)

2. Install `native-image` extension by GraalVM updater tool

```bash
gu install native-image
```

3. Install docker


## Build and Run as a Native Executable

1. Run the following command:

```shell
export GRAALVM_HOME=/Library/Java/JavaVirtualMachines/graalvm-ce-java17-22.3.1/Contents/Home
export JAVA_HOME=/Library/Java/JavaVirtualMachines/graalvm-ce-java17-22.3.1/Contents/Home
./gradlew nativeRun
```

A binary executable would be generated in `target` folder

2. Run the binary to start the app

```shell
./fortune/build/native/nativeCompile/fortune
```
