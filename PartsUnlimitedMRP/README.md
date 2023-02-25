# PartsUnlimitedMRP

## GitHub Repository

https://github.com/SarahBornais/PartsUnlimitedMRP

## Requirements

Java 8, mongodb

## Instructions

First, clone the forked repository:

```
git clone https://github.com/SarahBornais/PartsUnlimitedMRP
cd PartsUnlimitedMRP
```


### Building

We must build three separate services: `OrderService`, `IntegrationService`, and `Clients`.

To build the `OrderService`:

```
cd src/Backend/OrderService
chmod +x gradlew
./gradlew build
```

The JAR file will be created at `src/Backend/OrderService/build/libs/ordering-service-0.1.0.jar`

To build the `IntegrationService`:

```
cd src/Backend/IntegrationService
chmod +x gradlew
./gradlew build
```

The JAR file will be created at `src/Backend/IntegrationService/build/libs//integration-service-0.1.0.jar`

To build the frontend `Clients`:

```
cd src/Clients
chmod +x gradlew
./gradlew build
```

The WAR file will be created at `src/Clients/build/libs/mrp.war`

### Running

Before running the application, we must first set up some data in the MongoDB database.

#### Setting Up the MongoDB Database
1.  Open the mongo command line tools by typing the following command:
    `/usr/bin/mongo`

2.  Select the ordering database to create it.
    `> use ordering`

3. Add an object to the catalog collection

```
> x = {"skuNumber" : "ACC-001", "description" : "Shelving", "unit" : "meters", "unitPrice" : 10.5 }
> db.catalog.insert(x)
```

4.  Check the object was created

    `> db.catalog.find()`

you should see something like:
```
{ "_id" : ObjectId("5568a7aefa7a8f99400cbd1e"), "skuNumber" : "ACC-001", "description" : "Shelving", "unit" : "meters", "unitPrice" : 10.5 }

```

5. Now there is data in the database you can check it with the following command
   `> show dbs`
   Which should show something similar to:
```
local   0.078125GB
ordering        0.203125GB
```

6.  Copy the commands from [MongoRecords.js](https://github.com/SarahBornais/PartsUnlimitedMRP/blob/master/deploy/MongoRecords.js) to insert sample data into the database

#### Running the Services

To run the `OrderService`:

```
cd src/Backend/IntegrationService/build/libs/
java -jar ordering-service-0.1.0.jar
```

To run the `IntegrationService`:

```
cd src/Backend/IntegrationService/build/libs/
java -jar integration-service-0.1.0.jar
```

The client `mrp.war` file can be run with your preferred method of running WAR files (eg. tomcat, glassfish).





