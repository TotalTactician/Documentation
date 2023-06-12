# CI/CD Implementation

## Table of Contents
- [Intro](#intro)
- [CI for Node.js](#ci-for-nodejs)
- [CD for Node.js](#cd-for-nodejs)

## Intro
Whilst I was creating the Frontend I thought it would be helpful to implement some form of automation in my toolkit using github actions. 

This automation allows me to automatically build my Node.js application and test it before I merge my code, ensuring that my code wont break production and catching problems I might not have seen during development.

It also automatically pushes a Dockerimage to Dockerhub making it easier to run any form of Production enviroment without having to spend a lot of time getting everything built and setup every time I update main.

## CI for Node.js
Code Snippet for CI as used on the [Svelte Frontend](https://github.com/TotalTactician/TOT_Frondend/tree/main) as of time of writing (31st of May, 2023)
```main.yml
name: Node.js CI

on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]

jobs:
  build:
    runs-on: ubuntu-latest

    strategy:
      matrix:
        node-version: [10.x, 12.x, 14.x, 15.x]
    defaults:
      run:
        working-directory: my-app
    steps:
      - uses: actions/checkout@v3
      - name: Use Node.js ${{ matrix.node-version }}
        uses: actions/setup-node@v3
        with:
          node-version: ${{ matrix.node-version }}
      - run: npm ci
      - run: npm run build --if-present
      - run: npm test
```

## CD for Node.js
With the workflow below whenever we push the dev branch to the main a Docker image gets built from the Docker file and pushed to a DockerHub repository. This is on the TOT_DockerPOC repository.

```yml
name: Publish Docker Image to Docker Hub

on:
  push:
    branches: ['main']

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3

      - name: Log in to Docker Hub
        uses: docker/login-action@f054a8b539a109f9f41c372932f1ae047eff08c9
        with:
          username: ${{ secrets.DOCKER_USERNAME }}
          password: ${{ secrets.DOCKER_PASSWORD }}

      - name: Build the Docker image
        run: docker build -t ${{ secrets.DOCKER_USERNAME }}/tot_dockerpoc -f TOT_DockerPOC/Dockerfile ./ --no-cache

      - name: Docker Push
        run: docker push ${{ secrets.DOCKER_USERNAME }}/tot_dockerpoc
```
This one runs whenever there is a push to main. In a standard scenario you want your CI to have succeeded before you allow the dockerimage to be made and pushed. To do this you replace the top part with the code below.
```yml
on:
  workflow_run:
    workflows: ["Node.js CI main"]
    types:
      - completed

jobs:
  docker_build:
    runs-on: ubuntu-latest
    if: ${{ github.event.workflow_run.conclusion == 'success' }}
```
In the image below you see the result of a succesful run of the CD workflow:
![image](https://github.com/TotalTactician/Documentation/assets/39733159/e67bf2b6-3794-4c5f-8f16-c7ae858b889b)

