# django-quick-deploy
This is a small repository to quickly deploy your django app using Docker Nginx and Gunicorn 

# Getting Started

1. Set your project name `export REPO_NAME=generic_repo`

2. Clone this repository `git clone https://github.com/appunni-dishq/django-quick-deploy.git` ${REPO_NAME}

3. (!Caution) Delete this .git repo files `rm -rf  ${PROJECT_NAME}/.git/`

3. Copy your existing django project into this new project`cp /path/to/django-project ${REPO_NAME}/ --recursive`

4. Optional - Copy your git files into the new project or `git init`


# Prerequisites

This considers that you have set

`STATIC_URL = '/static/'`

in you `${PROJECT_NAME}/${PROJECT_NAME}/settings.py

If you are using `django-storages` then you can set it as you would like.
But incase you need support for local static files, please keep it like this.

# Deployment

1. Set your env vars inside .env file, please also add it to .gitignore after `git rm --cached .env`

2. Below env vars are required by default replace localhost with your original domain name for deployment in production.

`ALLOWED_DOMAINS=localhost`
`SITES=localhost=app:8080`

3. Run `docker-compose up -d` and open https://localhost/admin in your browser or https://domain.com/admin

# Initializations

In order for production projects there are options to connect to Databases,
Currently this is a preview project, soon I will be adding functionality to help support those features

Inorder to create a new user use 