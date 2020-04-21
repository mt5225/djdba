# Development Setup with Docker, Django, MySQL and VSCode

## How to deloy on your laptop

- install docker desktop in you PC
- clone the repository
- run `docker-compose up -d` , that's it!
- open your browser and visit `http://localhost:8000`

## Setup

- Django 3.0 listen on port `8000`
- MySQL 8.0.19 listen on port `3306`, user/pass = mydjangoapp

## Change default port and user/pass setting

- Edit `docker-compose.yml` file in the root project folder
- Rebuild docker container: `docker-compose up --build --force-recreate -d`

or, you may try a **CLEAN** start as

- stop docker compose: `$ docker-compose down`
- remove ALL container and images: `$ docker system prune -a`
- start docker compose: `$ docker-compose up -d`
