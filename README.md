
# Installment

## Installing Docker
1- Install [Docker for your O.S](https://docs.docker.com/get-docker/).
2- Open a terminal and access this directory 
3- Run this command `docker-compose up -d`  and wait for everything to finish, although it´ll exit, the server will be running in the background
3- Access your WordPress in `http://localhost:8000`
3.bis- It'll probably ask you to setup the site, use this config and then click on "Instalar Wordpress":
```
Titulo del sitio: Security Tests
Nombre del usuario: admin
contrasena: admin
confirma la contrasena: si, checked
tu correo: pepe@gmail.com
visibilidad en motores: no, unchecked
```
4- Done, now login with user `admin` and password `admin`


## Usage

### Wordpress

#### Viewing the site
http://localhost:8000

#### Administration of the instance
http://localhost:8000/wp-admin/



# Notes

- Docker: 
  - We're using [the Docker image for WordPress that runs on php7.3 apache](https://github.com/docker-library/wordpress/blob/master/php7.3/apache/Dockerfile). It should be similar to the real environment