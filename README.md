# Django, Vue, nginx, Docker setup

Create a superuser:

```bash
docker ps # Get container ID
docker exec -it <container ID> /bin/bash
python manage.py createsuperuser
exit
```

If your django application uses a server hosted on the local machine. Use the following as the host:

```bash
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': config('DT_NAME'),
        'USER': config('DT_USER'),
        'PASSWORD': config('DT_PASS'),
        'HOST': "host.docker.internal",
        'PORT': config('PORT'),
    }
}
```

Generate a secret key:
```bash
python -c 'import secrets; print(secrets.token_urlsafe(38))'
```

add it to "docker-compose.yml" and run the following command:

```bash
docker-compose up --build
```
