# Development Setup with Docker, Django, MySQL and VSCode

## How to deloy on your laptop

- install VScode
- install docker desktop
- clone the repository
- run `docker-compose up -d` , that's it!

## Verify

- open your browser and visit `http://localhost:8000`
- exam container log `docker logs -f helloworld_web_1`

## Configuration

- Django 3.0 listen on port `8000` localhost
- MySQL 8.0.19 listen on port `13306` localhost, user/pass = mydjangoapp

## Useful command while doing development

### Python code change

you donot need to do anything cuz gunicorn will reload automatically in case of code change

### DB schema change or data init

Use mysql workbanch or something simular

### Django db migrations

```
docker exec -it helloworld_web_1 python manage.py makemigrations
docker exec -it helloworld_web_1 python manage.py migrate
```

`docker exec -it helloworld_web_1 id`

## MISC

### Login to container with shell

`docker exec -it helloworld_web_1 bash`

### Change default port and user/pass setting

- Edit `docker-compose.yml` file in the root project folder
- Rebuild db container: `docker-compose up --build -d db`
- Rebuild web container: `docker-compose up --build -d web`

or, you may try a **CLEAN** start as

- stop docker compose: `$ docker-compose down`
- remove ALL container and images: `$ docker system prune -a`
- start docker compose: `$ docker-compose up -d`
