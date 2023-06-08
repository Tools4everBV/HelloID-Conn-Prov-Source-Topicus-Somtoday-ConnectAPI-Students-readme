# HelloID-Conn-Prov-Source-Topicus-Somtoday-ConnectAPI-Students-readme

| :warning: Warning - **You need to sign a contract with the supplier before implementing this connector**|
|:---------------------------|
| This repository contains the connector and configuration code only. The implementer is responsible to acquire the connection details such as username, password, certificate, etc. Please contact the client's application manager to coordinate the connector requirements.       |

| :information_source: Contact |
|:---------------------------|
| Please contact your local Tools4ever sales representative for further information and details about the implementation of this connector  |
<br />
<p align="center">
  <img src="https://www.tools4ever.nl/connector-logos/somtoday-logo.png">
</p>

## Table of contents

- [HelloID-Conn-Prov-Source-Topicus-Somtoday-Students](#helloid-conn-prov-source-topicus-somtoday-students)
  - [Table of contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Getting started](#getting-started)
    - [Connection settings](#connection-settings)
    - [Prerequisites](#prerequisites)
    - [Remarks](#remarks)
  - [Setup the connector](#setup-the-connector)
  - [Getting help](#getting-help)
  - [HelloID docs](#helloid-docs)

## Introduction

_HelloID-Conn-Prov-Source-Topicus-Somtoday-Students_ is a _source_ connector. Topicus-Somtoday-Students provides a set of REST APIs that allow you to programmatically interact with its data. The connector retrieves the students from SOMToday. Because working with students and not with employees. There is no such thing as Employments and Positions. The connector formats the "subject choice", "class group", and placements *(vakkeuzes, lesgroepen, plaatsingen)* to HelloId contracts. This results in three different types of HelloID objects. During implementation, there must choose between those. Or make a combination of multiple, which represents a contract in HelloID.
This connector is built with active data and only example future data from a Test environment.



## Getting started

### Connection settings

The following settings are required to connect to the API.

| Setting      | Description                        | Mandatory   |
| ------------ | -----------                        | ----------- |
| ClientID     | The ClientID to connect to the API | Yes         |
| ClientSecret | The Password to connect to the API | Yes         |
| BaseUrl      | The URL to the API                 | Yes         |
| Instelling   | The Name of the organization       | Yes         |
| schoolYear   | Specify the period to received students (HUIDIG and VOLGEND)     | No         | (Script variable)



### Prerequisites
- As implementer, you need your own set of credentials before you can implement this connector. Therefore you need to sign a contract with the supplier.

### Remarks
 - Not each object in (Vakkeuzes) contains a UUID, which seem to be the unique ID. These (Vakkeuzes) do not have a unique id, what results in blocked contracts in HelloID. (This might be a issue of Test data in the Test environment).
- There is no calculation of the manager. Due to there being no manager relationship between students and a manager
- The "Vakkeuzes" object for each student contains a lot of data, which may be too much for processing around 3000 students and above, which results in a `System.OutOfMemoryException`. Therefore, if you do not require certain fields, please exclude it from the response. This can be done in the loop at row number 128. If you still require particular properties of (vakkeuzes) or a different Sub-object please use calculated property and specify only the field(s) required.

**See the following Example of an exclusion:**
```PowerShell
$responseStudents = [array](Invoke-TopicusStudentsRestMethod @splatRestParams -ResultCollectionName 'Leerlingen') | Select-Object * , @{Name = 'vakkeuzesUuid'; Expression = { $_.vakkeuzes.uuid } }  -ExcludeProperty adres, plaatsingen, vestiging, lesgroepen, verzorgers, vakkeuzes
```
**Calculated property:**
```PowerShell
Select-Object *, @{Name = 'vakkeuzesUuid'; Expression = { $_.vakkeuzes.uuid } }
```


## Setup the connector

> _How to setup the connector in HelloID._ Are special settings required. Like the _primary manager_ settings for a source connector.

## Getting help

> _For more information on how to configure a HelloID PowerShell connector, please refer to our [documentation](https://docs.helloid.com/hc/en-us/articles/360012557600-Configure-a-custom-PowerShell-source-system) pages_

> _If you need help, feel free to ask questions on our [forum](https://forum.helloid.com)_

## HelloID docs

The official HelloID documentation can be found at: https://docs.helloid.com/
