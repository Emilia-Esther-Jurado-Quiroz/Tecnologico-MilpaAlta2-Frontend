### Introducción

Este repositorio contiene ejemplo de como levantar contenedores con **Dockerfiles** del siguiente servicio:

**Angular**

### Requerimientos

Para poder levantar estos servicios, debe tener instalado el servicio de [Docker](https://docs.docker.com/get-docker/).

##### Angular

[Angular](https://angular.io/docs) es un framework de diseño de aplicaciones y una plataforma de desarrollo para crear aplicaciones de una sola página eficientes y sofisticadas.

### Marco Teórico

Un docker trabajan con imágenes, que son una especie de plantill o una captura del estado de un contenedor (equivalente a un **snapshot** de una maquina virtual). Existe un [DockerHub](https://hub.docker.com/) que es un servicio que provee Docker para encontrar y compartir imágenes con la comunidad.

Las imágenes almacenadas en el DockerHub ya estan construidas, pero se pueden crear de acuerdo a las necesidades del usuario.

Para contruir una imagen es necesario usar un archivo llamado Dockerfile el cual define el estado del cotenedor. La mayoria de las imagenes tienen como base un sistema operativo como:

contenedor **Centos**
```docker
FROM centos:latest
```

Contenedor **Debian**
```docker
FROM debian:latest
```

Para mayor referencia busque en [DockerHub](https://hub.docker.com/)

Angular no tiene una imagen prestablecida pero su instalacion se puede realizar en cualquie sistema operativo. El siguiente ejemplo es la definicion de una imagen que instala Angular 

```docker
FROM node:10.13-alpine as node-angular-cli

RUN apk update \
  && apk add --update alpine-sdk \
  && apk del alpine-sdk \
  && rm -rf /tmp/* /var/cache/apk/* *.tar.gz ~/.npm \
  && npm cache verify \
  && sed -i -e "s/bin\/ash/bin\/sh/" /etc/passwd

RUN npm install -g @angular/cli
```

Esta imagen se construye mediante el siguiente comando:

```sh
docker build -t angular .
```

Posteriormente se ejecuta el comando `run` el cual va a levantar el docker con el siguiente script y crear un proyecto en Angular:

```sh
docker run -it --rm -w /app -v `pwd`:/app angular ng new my-project-name
```

Como siguiente paso, se creaá un componte en Angular con el siguiente script

```sh
docker run -it --rm -w /app -v `pwd`/my-project-name:/app angular ng g component sample-component

```

Finalmente se expone en el servicio de Angular en el puerto 4200

```sh
docker run -it --rm -w /app -v `pwd`/my-project-name:/app -p 4200:4200 angular ng serve --host 0.0.0.0


```