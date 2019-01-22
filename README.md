Backend for [https://eahub.azurewebsites.net](https://eahub.azurewebsites.net)

![eahub.org reboot](https://i.imgur.com/02FNAlY.png)

# Setup
Make sure to have [Docker Compose](https://docs.docker.com/compose) installed.

# Running
```
$ docker-compose up
```

# Deploying
After uploading a new docker image, the website will automatically update
```
$ docker build -t eahub:latest .
$ y | docker system prune
$ docker tag eahub eahub.azurecr.io/eahub:latest
$ docker push eahub.azurecr.io/eahub:latest
```

# Running django commands
```
$ docker-compose run web bash
$ docker-compose run web django-admin shell
$ docker-compose run web django-admin makemigrations
$ docker-compose run web django-admin migrate
```

# Docker Image Registry Login
- Images are privately saved to our Azure Container Registry
```
$ docker login eahub.azurecr.io
>>> username: eahub
>>> password: <see lastpass>
```
