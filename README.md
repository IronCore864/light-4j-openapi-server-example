# Light-4J OpenAPI Server Example

## Dependencies

- JDK 8 or JDK 11
- codegen-cli (https://github.com/networknt/light-codegen, download the jar is the simplest way)
- mvn (optional, continue reading)

## Generate Code

java -jar YOUR/PATH/TO/codegen-cli.jar --framework openapi --output . --model ./openapi.json --config ./config.json

## Install and Run

If you have mvn installed:

```bash
mvn install exec:exec
```

else:

```bash
./mvnw install exec:exec
```

Following commands are the same.

## More on Build and Start

The scaffolded project contains a single module. A fat jar will be generated in target directory after running the build command below.

```bash
mvn clean install -Prelease
```

With the fat jar in the target directory, you can start the server with the following command:

```bash
java -jar target/server.jar
```

To speed up the test, you can avoid the fat jar generation and start the server from Maven:

```bash
mvn clean install exec:exec
```

## Test

By default, the OAuth2 JWT security verification is disabled, so you can use Curl or Postman to test your service right after the server is started. For example, the petstore API has the following endpoint.

```bash
curl -k https://localhost:8443/v1/pets
```
