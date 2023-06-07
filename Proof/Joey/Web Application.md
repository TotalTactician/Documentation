# Web Application

## Contents
- [Intro](#intro)
- [Application structure](#application-structure)
- [Frontend](#frontend)
-[ORM](#orm)

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
