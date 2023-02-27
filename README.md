# Case Study Package

## Introduction

We provide four case studies on which to run the decomposition tools:

| Case Study                                         | Instructions | GitHub Forked Repository | Framework | Number of Classes | Test Coverage |
| :-------------------------------------------------- | - | ----------- | --------- | ----------------- | ------------- | 
| 7ep-demo                | [Instructions](./7ep-demo/README.md) | [link](https://github.com/SarahBornais/demo)             | None      | 47                | 93%           |
| JPetStore                 | [Instructions](./JPetStore/README.md) | [link](https://github.com/SarahBornais/jpetstore-6)      | Spring    | 24                | 64%           | 
| PartsUnlimitedMRP | [Instructions](./PartsUnlimitedMRP/README.md) | [link](https://github.com/SarahBornais/PartsUnlimitedMRP)            | Spring    | 75                | 65%           | 
| spring-petclinic   | [Instructions](./spring-petclinic/README.md) | [link](https://github.com/SarahBornais/spring-petclinic)             | Spring    | 24                | 94%           | 



This repository contains all the information necessary to build, run, and test each of the case studies. All the
relevant information for each of the case studies is located under their respective directories in this repository.

## Step 1. Building, Running, and Testing the Case Studies

Depending on the needs of the microservice decomposition tool, it may be necessary to build, run, and/or test each of the
case study applications. Instructions on how to do so are located in the `README` file under each of the case studies'
respective directories.

The `/builds` directory under each of the case studies' directories contains pre-built JAR and/or WAR files, depending
on the type of application. These build files can be used as an input to the decomposition tools. If the tool requires additional input formats (e.g., instrumentation or similar), custom inputs can be created using the building, running, and testing instructions, as described above.

## Step 2. Reporting results

For consistency, we request that the tool's partitioning result be reported in a standard JSON format. We have provided
an example of such an output for each of the four case studies in a `reporting-template.json` file in their respective 
directories. These templates place all the classes in the given case study into a single partition, representing the
current monolithic state of the case studies.

An example of the JSON structure is provided below. The first key, `my_tool` is the name of the tool that created the 
decomposition. In this example, the decomposition contains 2 partitions: `partition0`, and `partition1`. If a decomposition contains more than
2 partitions, keys can `partition2`, `partition3`, etc. Each of the partition JSON objects contains
an array of JSON objects representing the classes contained in the decomposition. Each of these class objects has only a
single property, `id`, whose value is the name of the class it represents.

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
