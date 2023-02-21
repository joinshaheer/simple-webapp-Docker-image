# simple-webapp-Docker-image

# My Website
This is a simple Flask web application that can be run in a Docker container.

#Installation
To run the application locally, you'll need to have Docker installed on your machine. 
Once you have Docker installed, you can run the following command in the root directory of the repository to build the Docker image:

#docker build -t my-website .

This will build the Docker image using the Dockerfile in the repository, and tag it with the name my-website.
You can then run the Docker container using the following command:

$ docker run --name my-container -p 8080:8080 my-website

This will start the Docker container and expose port 8080,
which you can use to access the web application in your web browser at http://localhost:8080.

Usage
The web application is a simple Flask app that displays a "Hello, World!" message on the home page. 
You can modify the app.py file to change the content of the message or add additional functionality to the app.


01. Create a new directory:


mkdir my-website
cd my-website


02. Create a new file named app.py in the directory:


nano app.py
or 
vi app.py 


03. Paste the following code in the app.py file:


from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello():
    return 'Hello, World!'

if __name__ == '__main__':
    app.run(debug=True, host='0.0.0.0', port=8080)
   
Note: This code creates a simple Flask application that listens on port 8080 and returns a "Hello, World!" message when the root URL is requested.


04. Create a new file named Dockerfile in the directory:


nano Dockerfile
or 
vi Dockerfile

Paste the following code in the Dockerfile:

FROM python:3.6-alpine

RUN pip install flask

COPY . /opt/

EXPOSE 8080

WORKDIR /opt

ENTRYPOINT ["python", "app.py"]


Note: This code creates a Docker image that starts with the Alpine version of Python 3.6,
installs Flask using pip, and then copies the app.py file from the current directory to the /opt/ directory in the container.
The container's port 8080 is exposed, and the ENTRYPOINT runs the app.py file when the container starts.


05. Build the Docker image:


docker build -t my-website .

Note: my-website is the name you choose for the image.


07. Run the Docker container:


docker run --name my-container -p 8080:8080 my-website

Note: my-container is the name you choose for the container.

07. Open a web browser and go to http://localhost:8080 to see the "Hello, World!" message.



That's it! You have now built and run a simple website using Docker and Flask on Ubuntu.


