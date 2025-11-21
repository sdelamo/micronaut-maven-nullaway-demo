# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Micronaut 4.10.2 application demonstrating NullAway static analysis integration with Maven. It serves as a demo project showcasing null safety checking using JSpecify annotations and Error Prone/NullAway tooling.

## Key Technologies

- **Framework**: Micronaut 4.10.2 with Netty runtime
- **Build Tool**: Maven with micronaut-maven-plugin
- **Java Version**: JDK 21
- **Static Analysis**: Error Prone 2.29.2 + NullAway 0.12.12
- **Null Safety**: JSpecify 1.0.0 annotations
- **Testing**: JUnit 5 with micronaut-test

## Development Commands

### Build and Compilation
```bash
./mvnw compile
```

### Run the Application
```bash
./mvnw mn:run
```

### Run Tests
```bash
./mvnw test
```

### Package Application
```bash
./mvnw package
```

### Clean Build
```bash
./mvnw clean compile
```

## NullAway Configuration

The project is configured with NullAway static analysis that runs during compilation:
- **Annotated Package**: `example.micronaut` (configured in pom.xml line 98)
- **Processor**: Enabled via Error Prone compiler plugin
- **Annotations**: Uses JSpecify `@Nullable` and `@NonNull` annotations

## Architecture

The application follows standard Micronaut patterns:

### Core Components
- **Application.java**: Main application entry point
- **GreetingController**: HTTP controller with `@Get` endpoint at root path
- **GreetingService**: Business service marked as `@Singleton`
- **NullAwayDemo**: Demonstrates intentional null safety violations for testing NullAway

### Package Structure
- Main code: `src/main/java/example/micronaut/`
- All classes in the `example.micronaut` package are subject to NullAway analysis

### Dependency Injection
Uses Micronaut's built-in DI with constructor injection (see GreetingController.java:14)

## NullAway Behavior

When you run compilation, NullAway will flag null safety violations. The NullAwayDemo.java file contains intentional violations to demonstrate the tooling in action. Compilation may fail or produce warnings depending on NullAway configuration.