# Hello World on SAP BTP Kyma Runtime
This is a sample Hello World application for the SAP BTP Kyma Environment.
It features a minimal Node.js app with express, that prints a simple "Hello World" message in the browser.
That application will be containerized using docker and deployed to the Kyma Runtime in the SAP Business Technolgy Platform.

## Installation

Run the following command to install all dependencies and start the application locally.
```bash
yarn install
yarn start
```
After that, open http://localhost:3000 to access the application.

## Create Docker image

In order to deploy our application to the Kyma environment we need to create a Docker image first.

```bash
docker build . -t <your-user-name>/kyma-hello-world
```

Note: I pre-built the image and pushed it to the Docker registry as ``ebergmann/kyma-hello-world``.

## Start the Docker image

After the Docker image has been created, use the following command to run it and map port 3000 in the container to port 43000 on the host machine.

```bash
docker run -p 43000:3000 -d <your-user-name>/kyma-hello-world
```
After that, open http://localhost:43000 to access the application that is running inside the docker container.

