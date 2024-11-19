Web Service Load Balancer Prototype
Overview
This project demonstrates a simple setup with two Docker containers:

A web service running on Nginx, serving a static HTML page.
An Nginx load balancer that forwards traffic to the web service.
The entire setup can be run with a single command using Docker Compose.

Requirements
Docker installed (Get Docker).
Docker Compose installed (Install Docker Compose).
Docker Hub account (optional, for pushing images).

Project Structure

/web
  - index.html       # The HTML file served by the web service
  - Dockerfile       # Dockerfile to create the web service container
/loadbalancer
  - nginx.conf       # Nginx configuration for load balancing
  - Dockerfile       # Dockerfile to create the load balancer container
docker-compose.yml   # Docker Compose configuration
How to Run
Create the directory structure and files on your local machine:

webservice/ directory containing:
index.html
Dockerfile
loadbalancer/ directory containing:
nginx.conf
Dockerfile
docker-compose.yml in the root directory.
Make sure the file content matches what was provided earlier in the project setup.

Build and start the services:

In the root directory (where docker-compose.yml is located), open a terminal and run:


docker-compose up --build
This command will build the containers and start both the web service and the load balancer.

Access the services:

Direct access to the Web Service: Open your browser and go to http://localhost:8082 to access the static HTML page served by Nginx.
Access through Load Balancer: Go to http://localhost:9090 to access the web service via the Nginx load balancer.
Configuration
The web service serves a static HTML file located at webservice/index.html. You can edit this file to change the content of the page.
The load balancer is configured using loadbalancer/nginx.conf. You can modify this configuration if you need to change how requests are routed or add additional load balancing rules.
Port Mapping
Web Service: Accessible on http://localhost:8082
Load Balancer: Accessible on http://localhost:9090
Stopping the Services
To stop the running services, press Ctrl + C in the terminal where Docker Compose is running, or run:

docker-compose down
This will stop and remove the container.
