name: CI/CD Pipeline

on:
  push:
    branches:
      - main   # triggers when code is pushed to main

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v3

      - name: Setup Java
        uses: actions/setup-java@v3
        with:
          java-version: '17'

      - name: Build project
        run: |
          echo "Building project..."
          javac HelloWorld.java

  deploy:
    needs: build
    runs-on: ubuntu-latest

    steps:
      - name: Deploy step
        run: |
          echo "Deploying application..."
          echo "Deployment successful"
Hello 
I have added some more data
