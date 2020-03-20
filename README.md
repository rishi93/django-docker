# Django Docker tutorial
Deploying simplest possible Django webapp with Docker, Docker-Compose

## How to run a dockerized application
- Build the image. Perform this command where the Dockerfile resides.
```bash
docker build -t <image_name> .
```
A Docker image will be built from the Dockerfile instructions
- Run the image as a container
```bash
docker run --name <container_name> --publish 8000:8000 <image_name> [command]
```
Command in this case will be
```bash
python manage.py runserver 0.0.0.0:8000
```
- Additionally, these build and run commands with the port, volumes etc. could be written in a docker-compose file.  
In which case, to run the container, we use the command  
```bash
docker-compose up # To start the cluster
docker-compose down # To stop the cluster
```