# JPetStore

## GitHub Repository

https://github.com/SarahBornais/jpetstore-6

## Requirements

Java version must be one of: 11, 17, 19, 20, 21

## Instructions

First, clone the forked repository:

```
git clone https://github.com/SarahBornais/jpetstore-6
cd jpetstore-6
```

### Building

Run `./mvnw clean package`

The WAR file will be created at `target/jpetstore.war`

### Running

Run `./mvnw cargo:run -P tomcat90`

### Testing

Run `./mvnw clean verify -P tomcat90`