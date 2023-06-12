# Web Application

## Contents
- [Intro](#intro)
- [Application structure](#application-structure)
- [Frontend](#frontend)
- [ORM](#orm)
- [Communication front - and back end](#communication-front---and-back-end)
  - [REST versus GraphQL](#rest-versus-graphQL)

## Intro
In this document, I will explain the structure of our TotalTactitian application and our choices behind them.

## Application structure
We decided to use a microservice structure because we didn't use that yet and wanted to learn that. 
At the start, we thought about writing every microservice in a different language but decided that it would create extra complications, 
so we decided for the most part on Typescript with Express because the Svelte frontend also uses Typescript.

In the image below you can see the intended structure of our application. Due to time constraints, we have not implemented the DNS and Gateway. 
The task should be relatively quick to complete since we have previously dealt with similar issues during the group project. 
However, during that time, we had other pressing matters that took precedence in terms of priority.

![TOT-Structure drawio](https://github.com/TotalTactician/Documentation/assets/81526735/1deceb44-022c-4448-8f54-b33faeda9785)

In the image below you can see the initial design of the entities, this was then used as a start for the microsevice structure in general. 
In reality, there have been some changes, but overall, the essence of the design has remained largely consistent.

![image](https://github.com/TotalTactician/Documentation/assets/81526735/d25a28d2-c47b-413b-8220-451378c6de5a)

## Frontend
When considering the framework for the front end, we contemplated using either Vue or Svelte. After conducting thorough research, we discovered that they share several similarities. For detailed information, please refer to the full document available [here](https://github.com/TotalTactician/Documentation/blob/main/Research/Frontend%20Research.md).


We have also created designs for the pages, and an example can be found [here](https://github.com/TotalTactician/Documentation/blob/main/Proof/Joey/Requirements%20and%20Design.md#personal-project).

## ORM
Because we are using a Non-SQL Database we use an ODM (Object Data Manager) instead of an ORM. The only difference is that an ORM is used for relational databases like SQL and ODM is for document databases like MongoDB. 
At first, we tried to use Prisma, an ORM for Node.js but quickly found out that it doesn't work too well with MongoDB. And after a short search, we found Mongoose which is an ODM specifically made for MongoDB. Perfect!

This code can be found [here](https://github.com/TotalTactician/TOT_RaceManagement/tree/main/src).
In DAL is the call to the database and in Models is the schema for the Race model.

## Communication front - and back end
For Our personal project, we used only REST APIs, but while working on the Data microservice for our group project we got recommended GraphQL.

### REST versus GraphQL
REST API (Representational State Transfer) is an architectural style that has been widely used for building web services. It follows a client-server model where clients make requests to specific endpoints on the server, and the server responds with the requested data. REST API relies on predefined endpoints and uses HTTP methods like GET, POST, PUT, and DELETE to perform CRUD (Create, Read, Update, Delete) operations on resources.

On the other hand, GraphQL is a query language for APIs and a runtime for executing those queries with existing data. It allows clients to request exactly the data they need in a single request, avoiding over-fetching or under-fetching of data. With GraphQL, clients can define the structure of the response they desire by specifying the fields and relationships they want to retrieve from the server. This flexibility gives clients more control over the data they receive.

One key difference between REST API and GraphQL is how data is fetched. In REST, each endpoint typically returns a fixed set of data, and if the client needs additional information, it may require making multiple requests or receiving more data than necessary. GraphQL, on the other hand, allows clients to specify their data requirements precisely, reducing the amount of data transferred over the network and improving performance.
