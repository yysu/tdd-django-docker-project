# TDD-django-docker-project


## Tech stack
- Python 3.10
- Django 4.1.2
- Django REST Framework 3.14.0
- pytest
- Docker
- GitLab CI
- RESTful API
- [render](https://render.com/docs/deploy-django#update-your-app-for-render)


## API Overview

| Endpoint | HTTP Method | CRUD Method | Result |
| -------- | -------- | -------- | -------- |
| /api/movies | GET | READ | get all movies |
| /api/movies/:id | GET | READ | get a single movie |
| /api/movies | POST | CREATE | add a movie |
| /api/movies/:id | PUT | UPDATE | update a movie |
| /api/movies/:id | DELETE | DELETE | delete a movie |

## Folder structure
`git ls-tree -r --name-only HEAD | tree --fromfile`
```
.
├── .gitignore
├── README.md
├── app
│   ├── Dockerfile
│   ├── docker-compose.yml
│   ├── drf_project
│   │   ├── __init__.py
│   │   ├── asgi.py
│   │   ├── manage.py
│   │   ├── settings.py
│   │   ├── urls.py
│   │   └── wsgi.py
│   ├── manage.py
│   ├── movies
│   │   ├── __init__.py
│   │   ├── admin.py
│   │   ├── apps.py
│   │   ├── migrations
│   │   │   ├── 0001_initial.py
│   │   │   └── __init__.py
│   │   ├── models.py
│   │   ├── tests.py
│   │   └── views.py
│   └── requirements.txt
└── docker-compose.yml
```


## Note
If you use m1/m2 chip macbook, remember to `export DOCKER_DEFAULT_PLATFORM=linux/amd64` before building/running the image.