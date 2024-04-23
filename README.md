# Cloud Computing IA2 -- Adit Shah (21BCP419)
## Dockerfile for running three-tier-application
1. *From Node:* The Dockerfile begins by utilizing the official Node.js image from Docker Hub as the base for the Docker image being built, ensuring a suitable runtime environment for Node.js applications.
2. Workdir /app: The working directory inside the Docker container is set to /app, facilitating subsequent commands to be executed relative to this directory.
3. Copy . .: All files and directories from the current directory where the Dockerfile resides are copied into the /app directory within the Docker container, simplifying the setup process.
4. ENV MONGO_DB_USERNAME=admin & ENV MONGO_DB_PWD=password: Environment variables MONGO_DB_USERNAME and MONGO_DB_PWD are defined within the Docker container, specifying the username and password for MongoDB authentication as admin and password, respectively.
5. ENV MONGO_DB_PWD=password: The npm install command is executed inside the Docker container to install the dependencies listed in the package.json file located in the /app directory.
6. RUN npm install & Expose 3000: Ensure all necessary Node.js packages are installed and Docker is informed that the container listens on port 3000 at runtime, although the port is not published; it serves as documentation for users of the image.
7. CMD ["node", "server.js"]: The default command to run when the Docker container starts is specified as an array, where the first element is the command (node) and the second element is the script or file (server.js) to execute, initiating the Node.js application.

