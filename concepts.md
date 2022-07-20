# Data Access Service Concepts

## Contents

- Introduction
  - Relational data access
    - Raw SQL
    - Query Builder
    - ORM
  - Data access in cloud
    - Cloud native applications
    - Lamda
    - Microservices
  - Data access service
    - Query Service
    - SQL Service
    - CRUD Service
  - Service Builder
    - automates
    - Scaffolding application. module, services and tests
    - input and output bindings
    - table bindings
    - simple CRUD services

- Data Access Application
  - File Structure
  - Application File
  - Module File
  - Service File

- Basics
  - JSON
    - Data Type
    - JSON Path
  - Databases
  
- Query Service

- SQL Service

- CRUD Service


- Development
  - Basic
  - Development of Data Access Application
  - Development of Business Client Application

- Deployment
  - DevTime Deployment
  - Runtime Development


## Introduction

### Relational Data Access

#### Raw SQL

SQL is the ultimate language for relational data access. However, using SQL in a programing language is awakard:

- Hard to edit and test
- Hard to convert data set to aggregate objects
- Tedious to map data fields

Simple is tedious; complex is hard.

#### ORM


#### Query Builder


### Data Access In Cloud

The rise of cloud has caused the rise of

- Database as a Service (DBaaS)

- cloud native application
  - twelve factors
  - serverless functions
  - microservices

tiny and many vs tranditional monolith application
needs for connection pooling products, such as RDS Proxy, PgBouncer


### Data Access Services

The data access service is a new way of working with relational database. The core ideas include

- Separating data access layer from the application and make it a backing service of the application

- Replacing tranditional data access and repository objects with standarized data access services

- standardized
- declarative
- sql first
- aggregate-oriented
- transaction-less
- developer-centric


 each with predefined use and structure.




## Data Access Application

A data access application is essentially a collection of data access services organized into data access modules. 
An application may include one or more modules; a module may include one or more services. The service may be a query service for retrieving data; a SQL command service; or a CRUD service for CRUD operation of aggregate.


The data access module provides a way to group the data access services.


## Development


## Deployment

### DevTime Deployment

### Runtime Deployment





## References

### CRUD Service

A repository service for CRUD operations of aggregate root objects.

#### Operations

- Read
- Create
- Update
- Merge
- Save

#### Optimistic Lock

using a version column, of number type 

#### Soft Delete

Using a softDelete column, char(1) or varchar;

#### Column Handling for Insert

- Autogen: honered unconditionally
- Version: 0
- SoftDelete: 'N'
- InsertValue: hornered unconditionally
- Sourced:
	- sourced: source value
	- unsourced: null


#### Column Handling for Update

- key: in where clause
- Version: increase by 1
- SoftDelete: ignored
- UpdateValue: hornered unconditionally
- Sourced:
	- sourced: source value
	- unsourced: null


#### Column Handling for Merge

- key: in where clause
- Version: increase by 1
- SoftDelete: ignored
- UpdateValue: hornered unconditionally
- Sourced:
	- sourced: source value
	- unsourced: unchanged

