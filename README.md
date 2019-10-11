# choish-blog
choish-blog is a 'full stack web application' for those who want a personal web blog and want to study a full stack web application.

it was developed using React, DRF (Django REST Framework).

you can also use the Docker to deploy applications

see the readme. you will know the deployment process.

## Demo
[http://choiseunghwan.tk/](http://choiseunghwan.tk/) <u>현재 AWS 호스팅 중지 상태입니다.</u>
<p align="center">
  <img src="https://drive.google.com/uc?authuser=0&id=1s6p0U1nzaWUr1jU9xMVzCkhuotu1tFuv&export=download" width="700" title="demo">
</p>

## Technologies

### Frontend
* React 16.8
* Redux 4.0
* Webpack 4.3
* Babel 7.4
* Nginx 

### Backend
* Python 3.6
* Django 2.2
* Django Rest Framework 3.9

### Others
* PostgreSQL 11
* Docker 18.09

### Structure

<p align="center">
  <img src="https://drive.google.com/uc?authuser=0&amp;id=1r0ZBKiV8Cp2qU6eqrkssnMeGH0v5wTo0&amp;export=download" width="700" title="system_structure">
</p>

<p align="center">
  <img src="https://drive.google.com/uc?authuser=0&amp;id=1jhE25ICl2y1ZmxKYhmmxKcECqRBBWDjt&amp;export=download" width="700" title="docker">
</p>


## Getting Started

### Installation
1. git clone. be sure to use the --recursive option to get the submodules together
```
git clone --recursive https://github.com/Choi-Seunghwan/choish-blog.git
```
2. run docker-compose.
```
docker-compose up --build -d
```
you can modify the image names of the frontend and backend by modifying the 'image' option in the docker-compse file.


## Deploying

### Modifying the env file

you must modify the env file in the config folder before deployment.

including secret keys and passwords in application code is a security risk. so, they are managed as environment variables in the env file.


#### Django Secret key
show env file. this is secret key of django.
```
DJANGO_SECRETKEY= THIS_IS_EXAMPLE_KEY=1s9&)l7!q-4#1q=46#5$=qv%1s01$05njw74+d#_w-5i$4ronEXAMPLE
```
[Django Secret Key Generator](https://www.miniwebtool.com/django-secret-key-generator/) 
you can generate a Django secret key from this website


#### automatically generated django superuser
this is first automatically generated Django SuperUser. you can access admin page with this auto-generated superuser.
Change password after connecting.
```
DJANGO_INITSUPERUSER=user
DJANGO_INITSUPERUSERPW=1234
DJANGO_INITSUPERUSEREM=mymail@email.com
```

### Deploying with the docker
you can deploy the application by pulling the docker image from the server.

1. push image to Docker Hub
```
docker push frontendImageName (the image name you set)
docker push backendImageName 
```
2. pull image (on the server)
```
docker pull frontendImageName 
docker pull backendImageName 
```
3. upload the docker-compose file and the config folder to the server (use something like github)

4. run docker-compose up (run in the background with the -d option)
```
docker-compose up -d
```
