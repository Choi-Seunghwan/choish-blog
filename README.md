# choish-blog
choish-blog is a 'full stack web application' for those who want a personal web blog and want to study a full stack web application.

it was developed using React, DRF (Django REST Framework).

you can also use the Docker to deploy applications

see the readme. You will know the deployment process.

## Demo
[http://choiseunghwan.tk/](http://choiseunghwan.tk/)

## Technologies

### Frontend
* Node 8.10
* React 16.8
* Redux 4.0
* Webpack 4.3
* Babel 7.4
* Nginx 

### Backend
* Python 3.6
* Django 2.2
* Django Rest Framework 3.9
* PostgreSQL 11
* Docker 18.09

## Getting Started

### Installation
1. git clone. be sure to get submodules with the --recursive option.
```
git clone --recursive https://github.com/Choi-Seunghwan/choish-blog.git
```
2. install the package to build react (node_modules folder is too large to push to github.)
```
cd choish-blog-frontend
yarn install
```
3. build react
```
yarn build
```
4. return to choish-blog folder
```
cd ..
```
5. run docker-compose.
```
docker-compose up --build -d
```
you can modify the image names of the frontend and backend by modifying the 'image' option in the docker-compse file.


## Deploying

### Modifying the env file
you must modify the env file in the config folder before deployment.

including secret keys and passwords in application code is a security risk. so, they are managed as environment variables in the env file.

open env file.
this is th secret key of django.
```
DJANGO_SECRETKEY= ...~~~~~
```
[Django Secret Key Generator](https://www.miniwebtool.com/django-secret-key-generator/) 
you can generate a Django secret key from this website

this is the first automatically generated Django SuperUser. you can access the admin page with this auto-generated superuser.
Change the password after connecting.
```
DJANGO_INITSUPERUSER=user
DJANGO_INITSUPERUSERPW=1234
DJANGO_INITSUPERUSEREM=mymail@email.com
```

#### Deploying with the docker
you can deploy the application by pulling the docker image from the server.

1. push image to Docker Hub
```
docker push frontendImageName (the image name you set)
```
2. pull image (on the server)
```
docker pull backendImageName 
```
3. upload the docker-compose file and the config folder to the server (use something like github)

4. run docker-compose up (run in the background with the -d option)
```
docker-compose up -d
```

## Todo

* add editor page and Admin Page (on frontend ).
i had developed an editor using the react-draft-wysiwyg library.
however, when adding content by drag-and-drop, there was an error when there was an image in the content.
so I was very frustrated.
i will redevelop the editor page and admin page using a different library.

* tag list
* category
* other inconveniences found during use