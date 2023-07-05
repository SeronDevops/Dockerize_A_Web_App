# Dockerize_A_Web_App

# Install Node.js

# Install Express.js Dependecies
npx express-generator-esmodules my-react-app

# Create Dockerfile

# Use an official Node.js runtime as a parent image
FROM node:latest

# Set the working directory to /app
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code to the working directory
COPY . .

# Expose port 3000
EXPOSE 3000

# Start the application
CMD [ "npm", "start" ]

# Create dockerignore file
**/node_modules/
**/dist
.git
npm-debug.log
.coverage
.coverage.*
.env

# Push Repository to VScode
git push <repo name> <branch name>

# Run Docker Command to Build Image
docker build -t my-react-app .

# Run Docker Command to run Container
docker run -p 3000 my-react-app

# Tag Docker Image
docker tag my-react-app:latest ssdevops1/latest

# Push Docker Image to Docker Hub
docker push ssdevops1/latest