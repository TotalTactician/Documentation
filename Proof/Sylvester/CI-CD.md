# CI/CD Implementation

## Table of Contents
- [Intro](#Intro)
- [CI for Node.js](#CI-for-Node.js)
- [CD for Node.js](#CD-for-Node.js)

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

