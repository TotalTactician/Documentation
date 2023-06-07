# Web Application

## Contents
- [Intro](#intro)
- [Application structure](#application-structure)

## Intro
In this document I will explain the structure of our TotalTactitian application and our choices behind them.

## Application structure
We decided to use a microservice structure because we didnt use that yet and wanted to learn that. At the start we thought about writing every microservice in a diffrent language but decided that it would create extra complications, so we decided for the most part on Typescript with express because we the Svelte frontend also uses Typescript.

In the image below you can see the intended structure of our application. Due to time constrains we have not implemented the DNS and Gateway.

![TOT-Structure drawio](https://github.com/TotalTactician/Documentation/assets/81526735/1deceb44-022c-4448-8f54-b33faeda9785)

For choosing the framework for frontend we were thinking about using Vue or Svelte. The full document can be found [here](https://github.com/TotalTactician/Documentation/blob/main/Research/Frontend%20Research.md).

For accessing the data in the database I used a ODM called Mongoose code for that [here](https://github.com/TotalTactician/TOT_RaceManagement/tree/main/src),
In DAL is the call to the database and in Models is the schema for the Race model.
