# IMDb Movie Dataset Visualization

In this project, it is aimed to make web based visualization using imdb movie dataset.
Django was used as backend development and Angular as frontend development.

## Backend

### Requirements
* Python3.6
* Django
* Postgres

### Installation

#### Postgres

```sh
$ sudo apt-get update
$ sudo apt-get install python-pip python-dev libpq-dev postgresql postgresql-contrib
```

 Log into a Postgres session by typing:

 ```sh
 $ sudo su - postgres
 $ psql
 ```

 Create database and user:

 ```sh
 $ CREATE DATABASE myproject;
 $ CREATE USER myprojectuser WITH PASSWORD 'password';
 $ ALTER ROLE myprojectuser SET client_encoding TO 'utf8';
 $ ALTER ROLE myprojectuser SET default_transaction_isolation TO 'read committed';
 $ ALTER ROLE myprojectuser SET timezone TO 'UTC';
 $ GRANT ALL PRIVILEGES ON DATABASE myproject TO myprojectuser;
 $ ALTER USER myprojectuser CREATEDB;
 $ exit
 ```

 After this, on your settings.py:

  ```
  DATABASES = {
      'default': {
          'ENGINE': 'django.db.backends.postgresql_psycopg2',
          'NAME': 'myproject',
          'USER': 'myprojectuser',
          'PASSWORD': 'password',
          'HOST': 'localhost',
          'PORT': '5432',
      }
  }
  ```

### Run
To run backend:

```sh
$ python3 manage.py makemigrations or python3 manage.py makemigrations backend
$ python3 manage.py migrate
$ python3 manage.py createsuperuser
$ python3 manage.py runserver
```

To run backend tests:

```sh
$ python3 manage.py test
```

Go **http://127.0.0.1:8000/** on your browser.


## Frontend

### Requirements
* Angular CLI: v10.2.0
* Node v12.8.1
* npm v6.10.2

```sh
$ ng --version
```
![Picture](/angular.png)

### Installation

```sh
$ npm install -g @angular/cli
$ ng add @angular/material
$ npm install --save ng2-charts
$ npm install --save chart.js
```

### Run
To run frontend:

```sh
$ npm install
$ ng serve
```

Go **http://127.0.0.1:4200/** on your browser.

To run frontend tests:

```sh
$ ng test
```
