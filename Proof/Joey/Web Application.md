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
We decided to use a microservice structure because we didn't use that yet and wanted to learn that. At the start, we thought about writing every microservice in a different language but decided that it would create extra complications, so we decided for the most part on Typescript with Express because the Svelte frontend also uses Typescript.

In the image below you can see the intended structure of our application. Due to time constraints, we have not implemented the DNS and Gateway.

![TOT-Structure drawio](https://github.com/TotalTactician/Documentation/assets/81526735/1deceb44-022c-4448-8f54-b33faeda9785)

## Frontend
For choosing the framework for the front end we were thinking about using Vue or Svelte. We did some research and found that they are pretty similar

The full document can be found [here](https://github.com/TotalTactician/Documentation/blob/main/Research/Frontend%20Research.md).

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
