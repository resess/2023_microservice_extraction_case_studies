# Case Study Package

## Introduction

We provide four case studies on which to run the decomposition tools:

| Case Study                                         | Instructions | GitHub Forked Repository | Framework | Number of Classes | Test Coverage |
| :-------------------------------------------------- | - | ----------- | --------- | ----------------- | ------------- | 
| 7ep-demo                | [Instructions](./7ep-demo/) | [link](https://github.com/SarahBornais/demo)             | None      | 47                | 93%           |
| JPetStore                 | [Instructions](./JPetStore/) | [link](https://github.com/SarahBornais/jpetstore-6)      | Spring    | 24                | 64%           | 
| PartsUnlimitedMRP | [Instructions](./PartsUnlimitedMRP/) | [link](https://github.com/SarahBornais/PartsUnlimitedMRP)            | Spring    | 75                | 65%           | 
| spring-petclinic   | [Instructions](./spring-petclinic/) | [link](https://github.com/SarahBornais/spring-petclinic)             | Spring    | 24                | 94%           | 

The Instructions column in the table above contains a link to a directory we created, which includes instructions on how to build, run, and test the corresponding case study. The GitHub Forked Repository column in the table above, as well as each case study Instructions directory, also contains a link to the forked version of the case study repository in GitHub.

## Step 1. Building, Running, and Testing the Case Studies

Depending on the needs of the microservice decomposition tool, it may be necessary to build, run, and/or test each of the case study applications. Instructions on how to do so are located in the `README` file under each of the case studies' Instructions directories.

The Instructions’ `/builds` directory contains pre-built JAR and/or WAR files, depending on the type of application. These build files can be used as an input to the decomposition tools. If a tool requires additional input formats (e.g., instrumentation or similar), custom inputs can be created using the building, running, and testing instructions, as described in each case study Instructions directory (note: please use forked repository linked in the table above to perform any of these tasks).

## Step 2. Reporting results

Please report the tool partitioning result in the standard JSON format specified below. We have provided a template JSON output file, named `reporting-template.json`, pre-populated with the names of the classes of a case study, in its corresponding Instructions directory. These templates place all the classes of the given case study into a single partition, representing the current monolithic state of the case studies.

An example of the JSON structure is provided below. The first key, `my_tool` is the name of the tool that created the decomposition. In this example, the decomposition contains 2 partitions: `partition0`, and `partition1`. If a decomposition contains more than 2 partitions, additional keys such as `partition2`, `partition3`, etc., can be added. Each of the partition JSON objects contains an array of JSON objects representing the classes contained in the decomposition. Each of these class objects has only a single property, `id`, whose value is the name of the class it represents.

```json
{
  "my_tool": {
    "decomposition": {
      "partition0": [
        {
          "id": "ClassA"
        },
        {
          "id": "ClassB"
        }
      ],
      "partition1": [
        {
          "id": "ClassC"
        },
        {
          "id": "ClassD"
        }
      ]
    }
  }
}
```
