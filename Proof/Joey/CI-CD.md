# CI/CD implementation
## Contents
- [CI](#ci)
- [CD](#cd)
## Intro
I have implemented CI on the Race microservice and before implementing CD on here I made a proof of concept for it.

The original ```.yml``` files are located (here)[https://github.com/TotalTactician/TOT_RaceManagement/tree/dev/.github/workflows] for CI and (here)[https://github.com/TotalTactician/TOT_DockerPOC/tree/main/.github/workflows] for CD, though I will provide a snippet down below.

## CI
```yaml
name: Node.js CI dev

on: 
  push: 
    branches: [ dev ]
  pull_request:
    branches: [ dev ]
    
jobs:
  build:

    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v3
      - name: Use Node.js
        uses: actions/setup-node@v3
        with:
          node-version: '18.x'
      - run: npm i
      - run: npm run build --if-present
      - run: npm test
```

## CD
```yaml
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
![image](https://github.com/TotalTactician/Documentation/assets/81526735/9a553adf-2816-4a39-aada-27d603a42858)
