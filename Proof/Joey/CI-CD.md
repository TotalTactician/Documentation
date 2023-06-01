# CI/CD implementation
## Contents
- [Intro](#intro)
- [CI](#ci)
- [CD](#cd)
## Intro
I have implemented CI on the Race microservice and before implementing CD on here I made a proof of concept for it.

The original ```.yml``` files are located [here](https://github.com/TotalTactician/TOT_RaceManagement/tree/dev/.github/workflows) for CI and [here](https://github.com/TotalTactician/TOT_DockerPOC/tree/main/.github/workflows) for CD, though I will provide a snippet down below.

## CI
With this workflow the code gets tested every time there is a pull request opened to the dev branch and when someone pushes to the dev branch.
so we can make sure the code works before we merge it into the rest of the code, preventing major bugs.
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
With the workflow below when ever we push the dev branch to main a Docker-image gets build from the Docker-file and pushed to a DockerHub repository.
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
You only want the image to be build and pushed if the tests succeeded, but in this POC there are no tests. in the code snipped below you can see how this would be set up. 
where the workflow is triggered when the testworkflow is completed and only run the jobs if it succeeded.
```yaml
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
in the image below you see the result image of the CD workflow.
![image](https://github.com/TotalTactician/Documentation/assets/81526735/9a553adf-2816-4a39-aada-27d603a42858)
