# Node.js Dockerized Application

This repository contains a Dockerfile to build a Docker image for a Node.js application. This image is based on the official Node.js image from Docker Hub.

## Usage

### Building the Docker Image

To build the Docker image, make sure you have Docker installed on your system. Then, run the following command in the terminal:

```bash
docker build -t node-app .
```

### Running the Docker Container

Once the image is built, you can run the Docker container using the following command:

```bash
docker run -p 3000:3000 node-app
```

This will start the Node.js application inside the container and map port 3000 from the container to your host system.

### Accessing the Application

You can now access the application by visiting `http://localhost:3000` in your web browser.

## Dockerfile Explanation

### `FROM node`

This line specifies that our image will be based on the official Node.js image available on Docker Hub.

### `WORKDIR /app`

Sets the working directory inside the container to /app. This is where our application code will be copied.

### `COPY package*.json . and COPY yarn*.lock .`

Copies the package.json and yarn.lock files from the local directory into the /app directory in the container.

### `RUN yarn`

Installs the dependencies specified in package.json using the yarn package manager.

### `COPY . .`

Copies all the files and folders from the local directory into the /app directory in the container. This includes your application code.

### `EXPOSE 3000`

Informs Docker that the application will use port 3000. This is just a metadata declaration and does not actually publish the port.

### `CMD ["yarn", "dev"]`

Specifies the default command to run when the container starts. In this case, it will run the yarn dev command, assuming that it is defined in your package.json file.

## Contributing

If you find any issues or have suggestions for improvements, feel free to open an issue or create a pull request.
