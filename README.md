
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

# Initialize/run your application

- Set up your virtual environment
- `python3 -m venv .venv`

- Enter your virtual environment
- `source ./.venv/bin/activate`

- Install requirements
- `pip install -r requirements.txt`

- Start Docker
- `docker compose up`

- Run migrations on initial startup of docker
- `docker compose run web python manage.py migrate`

- Create your superuser (for testing recommend using: Username: admin1 : email: admin1@admin.com : password: 1234)
- `docker compose run web python manage.py createsuperuser`

- To check authentication status
- `http get http://127.0.0.1:8000/api/v1/drummer_app/

- To get token
- `http post localhost:8000/api/token/ username=admin1 password=1234`

- Copy access token without the quotes and run (don't forget about the closing single quote)
- `http://127.0.0.1:8000/api/v1/drummer_app/ 'Authorization: Bearer pasteAccessTokenOverThisString'`

- CRUD endpoint route:
- `api/v1/drummer_app/`

# Tests

N/A

