# deploying to Dockerhub

## table of contents
- [Before we start](#before-we-start)
- [Setting up a dockerhub repository](#setting-up-a-dockerhub-repository)
- [Adding credentials](#adding-credentials)
- [Setting up workflow](#setting-up-workflow)

## Before we start
in order for this to work you need 2 things:
- a project with a dockerfile
- a dockerhub acount

## setting up a dockerhub repository
first lets create a dockerhub repository.

I would give this the same name as the Github repository.

## Adding credentials
 In the Github repo go to settings -> secrets -> variables -> Actions
 
 here you create 2 repository secrets:
 - DOCKER_USERNAME = your dockerhub username
 - DOCKER_PASSWORD = your dockerhub password

once added they cant be read, only deleted or rewritten.

## Setting up workflow
