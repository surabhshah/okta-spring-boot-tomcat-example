# Run Spring Boot in Tomcat

This repository shows how to create a WAR file from a Spring Boot 2.1 project for deployment in Tomcat.  Please read [Deploy a Spring Boot Application into Tomcat](https://developer.okta.com/blog/2019/04/16/spring-boot-tomcat) to see how this example was created.

**Prerequisites:** [Java 11](https://adoptopenjdk.net/).

> [Okta](https://developer.okta.com/) has Authentication and User Management APIs that reduce development time with instant-on, scalable user infrastructure. Okta's intuitive API and expert support make it easy for developers to authenticate, manage, and secure users and roles in any application.

* [Getting Started](#getting-started)
* [Links](#links)
* [Help](#help)
* [License](#license)

## Getting Started

To install this example, run the following commands:

```bash
git clone https://github.com/oktadeveloper/okta-spring-boot-tomcat-example.git
cd okta-spring-boot-tomcat-example
```

To run this example, you'll need to create an account and OIDC app on Okta.

### Create an Application in Okta

Log in to your Okta Developer account (or [sign up](https://developer.okta.com/signup/) if you don’t have an account).

1. From the **Applications** page, choose **Add Application**.
2. On the Create New Application page, select **Web**.
3. Give your app a memorable name, add `http://localhost:8080/login/oauth2/code/okta` as a Login redirect URI, then click **Done**.

Copy your issuer (found under **API** > **Authorization Servers**), client ID, and client secret into `src/main/resources/application.yml` as follows:

```yaml
okta:
  oauth2:
    issuer: https://{yourOktaDomain}/oauth2/default
    client-id: {yourClientID}
    client-secret: {yourClientSecret}
```

**NOTE:** The value of `{yourOktaDomain}` should be something like `dev-123456.okta.com`. Make sure you don't include `-admin` in the value!

After modifying this file, start the example and you should be able to authenticate with Okta at `http://localhost:8080`.

### Packaging

To package the project (and create the WAR) run the following:

```bash
./mvnw clean package
```

The WAR file will be created in the `target` directory.

## Links

This example uses the following open source libraries:

* [Okta Spring Boot Starter](https://github.com/okta/okta-spring-boot) 
* [Spring Boot](https://spring.io/projects/spring-boot)
* [Spring Security](https://spring.io/projects/spring-security)
* [OpenJDK](https://openjdk.java.net/)

## Help

Please post any questions as comments on the [blog post](https://developer.okta.com/blog/2019/04/16/spring-boot-tomcat), or on the [Okta Developer Forums](https://devforum.okta.com/).

## License

Apache 2.0, see [LICENSE](LICENSE).
