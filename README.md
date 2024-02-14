# Flask on Docker

## Overview

This repository is an attempt at recreating an Instagram tech stack. I do this by containerizing a Flask application for development with Docker and Posgres. The production environment intigrates Gunicorn and Nginx.

The following gif is an example of uploading an image to the application and seeing in the browser:  

![Flask-on-Docker-gif](https://github.com/elissayz/flask-on-docker/assets/123142568/112e4325-85db-4276-a9ec-bdb8dd758e82)


If you would like to see a clearer version of this gif, it can be found [here](https://github.com/elissayz/flask-on-docker/assets/123142568/6405dfe4-eed0-4318-9945-1045b2c4d722).

## Build Instructions:

Both Flask and Docker are required to complete this project.

Here we use the default Flask development server.

Now we want to build and run the containers: 

```
$ docker-compose up --build
```

## Production:

After implementing the production files we need to build the images and run the containers again: 

```
$ docker-compose -f docker-compose.prod.yml up -d --build
$ docker-compose -f docker-compose.prod.yml exec web python manage.py create_db
```

## Testing:

To upload the file, navigate to the following page on your browser: http://localhost:3648/upload

Once you have uploaded the file, you can view it in browser at this page: http://localhost:3648/media/IMAGE_FILE_NAME

## Additional Credits: 

If you would like to attempt this same project, you can follow [this](https://testdriven.io/blog/dockerizing-flask-with-postgres-gunicorn-and-nginx/) tutorial.

I refrenced [this](https://github.com/testdrivenio/flask-on-docker/blob/main/README.md) README file to create my own.  
