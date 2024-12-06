# my-node-app
# Project 2: Dockerize a Web Application

This repository contains a simple Node.js web application, demonstrating how to containerize a web application using Docker.

## **Overview**
The goal of this project is to learn containerization by deploying a basic Node.js application inside a Docker container.

## **Getting Started**

### Prerequisites
Ensure the following tools are installed:
- [Node.js](https://nodejs.org/) (v16 or later)
- [npm](https://www.npmjs.com/) (comes with Node.js)
- [Docker Desktop](https://www.docker.com/products/docker-desktop)

### Installation Steps

1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd my-node-app
   ```

2. Install dependencies:
   ```bash
   npm install
   ```

3. Run the application locally to test:
   ```bash
   node app.js
   ```
   Access the application in your browser at [http://localhost:3000](http://localhost:3000).

### **File Structure**

```
my-node-app/
├── public/
│   └── index.html
├── app.js
├── package.json
├── package-lock.json
├── Dockerfile
└── README.md
```

## **Dockerizing the Application**

### 1. Build the Docker Image
Run the following command in the project directory (where the `Dockerfile` is located):
```bash
docker build -t my-web-app .
```

### 2. Run the Docker Container
Start the container and map the app’s port to your local machine:
```bash
docker run -p 3000:3000 my-web-app
```

### 3. Access the Application
Open your browser and navigate to:
[http://localhost:3000](http://localhost:3000)

## **Dockerfile**
The `Dockerfile` specifies the instructions to build the Docker image:
```dockerfile
FROM node:16
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY . .
EXPOSE 3000
CMD ["node", "app.js"]
```

## **What You’ll Learn**
- Setting up a basic Node.js application.
- Writing a `Dockerfile` to containerize the application.
- Building and running Docker containers.

## **Next Steps**
- Experiment with multi-stage builds to optimize the image size.
- Use environment variables to make the app configurable.
- Push the Docker image to a container registry (e.g., Docker Hub).

## **Troubleshooting**
If you encounter any issues:
1. Ensure all dependencies are installed correctly.
2. Verify Docker installation with:
   ```bash
   docker --version
   ```
3. Check the `package.json` and `Dockerfile` for syntax errors.

Feel free to create an issue in the repository for further assistance.

