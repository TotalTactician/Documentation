# Web Application Proof

## Table of Contents
- [Intro](#intro)
- [Application Architecture](#application-architecture)
- [Front-end](#front-end)
- [Back-end](#back-end)
- [Communication between Front and Back](#communication-between-front-and-back)

## Intro
During this project we setup a web application, whilst it is not done and not everything is implemented we have a clear vision of where we wanted to take this next. So some of the schemes are not yet fully implemented.

## Application Architecture
Below you can see the original scheme for a SQL database that we were planning to use originally. After some reconsideration we changed to using NoSQL and microservices making a large structured database unnecessary. However this scheme has still been helpful in guiding us trough the many different entities we have.

![image](https://github.com/TotalTactician/Documentation/assets/39733159/0743c353-9640-4aef-a959-f9c3e2ef9cca)

In the scheme below you can see our architecture that we landed on after some time. We decided that we wanted to use the Gateway pattern in our microservice based architecture because this pattern allows us to solves some issues around microservices like Aggregation and Composition and allows us to do things like Load balancing, better Security and Access control. 

![image](https://github.com/TotalTactician/Documentation/assets/39733159/b90ef505-72a2-431a-ba11-ba2c3555b97d)

## Front-end
The framework we used for our front-end is Svelte. We did some research into both Vue and Svelte and found they are pretty similar but Svelte has the ability to be used to create more reactive pages. 
You can read our short research about the two [here](https://github.com/TotalTactician/Documentation/blob/main/Research/Frontend%20Research.md)

## Back-end
Our backends are made in Typescript with Express and Python with Flask. We used two different languages for our backends because we wanted to experiment a bit. Due to this we had to use one unified communication style across the different services which became JSON. In the Typescript Microservice we first looked at Prima, but after looking around some more we found out about Mongoose which is an ODM made for MongoDB, which is the database we were using. When setting up the Python microservice we knew we needed a ODM for mongo that works in Python and we found PyMongo to fill that gap perfectly.

## Communication between Front and Back
We originally (and still) wanted to implement a Gateway with a DNS service. We made this in the group project aswell, however we sadly didnt have the time to adapt it into our project. The plan was to have standard HTTPS communication with the gateway and the look into different, faster, communication protocols to communicate with the various microservices. Right now we have the two microservices that communicate using HTTP with the front-end using the Fetch API.


