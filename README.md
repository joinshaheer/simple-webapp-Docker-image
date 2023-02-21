# simple-webapp-Docker-image

# My Website
This is a simple Flask web application that can be run in a Docker container.

#Installation
To run the application locally, you'll need to have Docker installed on your machine. 
Once you have Docker installed, you can run the following command in the root directory of the repository to build the Docker image:

#docker build -t my-website .

This will build the Docker image using the Dockerfile in the repository, and tag it with the name my-website.
You can then run the Docker container using the following command:

# docker run --name my-container -p 8080:8080 my-website

This will start the Docker container and expose port 8080,
which you can use to access the web application in your web browser at http://localhost:8080.

Usage
The web application is a simple Flask app that displays a "Hello, World!" message on the home page. 
You can modify the app.py file to change the content of the message or add additional functionality to the app.

