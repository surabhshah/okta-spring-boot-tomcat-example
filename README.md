# Run Spring Boot in Tomcat

This repository shows how to create a WAR file from a Spring Boot 2.1 project
for deployment in Tomcat.

## Authentication

Here Okta is used for authentication. Make sure to edit `src/main/resources/application.yml`
with your Okta application credentials.

## Packaging

To package the project (and create the WAR) run the following:

```bash
./mvnw clean
./mvnw package
```

The WAR file should be in the `target` directory.