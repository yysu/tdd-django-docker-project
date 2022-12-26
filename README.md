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


## Some useful command
```
# Start app
$ docker-compose up -d --build

# Run the tests with coverage
$ docker-compose exec movies pytest -p no:warnings --cov=.

# Want to view an HTML version
$ docker-compose exec movies pytest -p no:warnings --cov=. --cov-report html

# Run Flake8
$ docker-compose exec movies flake8 .

# run Black
$ docker-compose exec movies black --check --exclude=migrations .

# Try running it with the diff option as well before applying the changes
$ docker-compose exec movies black --diff --exclude=migrations .
$ docker-compose exec movies black --exclude=migrations .


# Run it with the check-only and diff options
$ docker-compose exec movies isort . --check-only
$ docker-compose exec movies isort . --diff

# apply the changes
$ docker-compose exec movies isort .


# Verify one last time that Flake8, Black, and isort all pass:
$ docker-compose exec movies flake8 .
$ docker-compose exec movies black --check --exclude=migrations .
$ docker-compose exec movies isort . --check-only
```