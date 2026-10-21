# Config Server

A Spring Cloud Config Server that serves centralized configuration to the microservices of this practice project.

## Overview

Instead of keeping settings inside each service, the services ask this server for their configuration at start-up. The server reads the property files from a Git repository: [cloud-config](https://github.com/danishahm89/cloud-config).

## Tech stack

- Java 17
- Spring Boot 3.3.2
- Spring Cloud 2023.0.3 (Config Server)
- Spring Boot Actuator
- Maven

## Configuration

| Setting | Value |
|---|---|
| Application name | `config-server` |
| Port | `8888` |
| Git repository | `https://github.com/danishahm89/cloud-config` |
| Branch | `main` |
| Clone on start | `true` |

## Run locally

The application is in the `config-server` folder.

```bash
cd config-server
mvn spring-boot:run
```

Check that configuration is served:

```bash
curl http://localhost:8888/account-management/default
curl http://localhost:8888/customer-management/default
```

## Related repositories

- [cloud-config](https://github.com/danishahm89/cloud-config): the configuration files served by this server
- [eureka-server](https://github.com/danishahm89/eureka-server): service discovery
- [api-gateway](https://github.com/danishahm89/api-gateway): single entry point for the services

## Concepts shown

- Centralized, externalized configuration with Spring Cloud Config
- Git-backed configuration
- Separating configuration from application code
