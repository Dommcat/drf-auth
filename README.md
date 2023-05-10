
# 401 Advanced Python LAB - Class 33

## Author: Dominck Martin

## Project: Django Authentication and Production Server 

## Feature Tasks and Requirements

## Django
 - Add JWT Authentication to your API.
 - Install needed libraries in project configuration and/or site settings
 - Keep any pre-existing authentication so DRF Browsable API still usable
 - Install needed libraries in project configuration and/or site settings

 ## Docker
 - Switch to using Gunicorn instead of Django’s built in development server
 - Mind the number of workers to avoid sluggishness
 - On Django side you’ll need to properly handle static files using Whitenoise

### Storage Options
- Your choice of SQLite or PostgreSQL
- Adjust docker-compose.yml so that data is persisted in a volume outside of container
- These steps are different depending on whether SQLite or PostgreSQL is being used

##  Setup

docker compose up --build

Need to set up .env file in project folder for Django secret key.  See .env.sample

## Initialize/run your application

- Build docker container: docker compose up --build
- With docker running: docker compose run web python manage.py migrate
- With docker running: docker compose run web python manage.py createsuperuser


Routes:

- To check authentication status `http get http://127.0.0.1:8000/api/v1/drummer_app/`

- Get a token: http post localhost:8000/api/token/ username=admin password=YOUR_PASSWORD

- Refresh token: http post localhost:8000/api/refresh/ refresh=REFRESH_TOKEN_HERE

- Admin: `http://127.0.0.1:8000/admin`

- CRUD endpoint route: `api/v1/drummer_app/`