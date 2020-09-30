# Tecnológico-MilpaAlta2-Frontend

Este repositorio es creado para ejemplificar las clases a los alumnos del Tecnológico de Milpa Alta 2.

1. [Docker Mongo](https://github.com/Juls-Castor/Tecnologico-MilpaAlta2-LenguajesAutomatas/blob/master/README.md)
2. Docker Angular
3. Docker Mongo


### Introducción

Este repositorio contiene ejemplos de como levantar contenedores con **Dockerfiles** de los siguientes servicios:

* Angular
* Mongo

#####Requerimientos

Para poder levantar estos servicios, debe tener instalado el servicio de [Docker](https://docs.docker.com/get-docker/).

#####Angular

[Angular](https://angular.io/docs) es un framework de diseño de aplicaciones y una plataforma de desarrollo para crear aplicaciones de una sola página eficientes y sofisticadas.

#####Mongo

[MongoDB](https://www.mongodb.com/) es una base de datos distribuida, de propósito general, basada en documentos, creada para desarrolladores de aplicaciones modernas y para la era de la nube.

### Marco Teórico

Existe una imagen para contenedores con el servicio de [MongoDB](https://hub.docker.com/_/mongo), el cual se puede obtener corriendo el siguiente script (asumiendo que tiene docker instalado).


```
docker pull mongo
```



Posteriormente, inicializa el docker con el siguiente comando:

```
docker run -d --name mongodb -e MONGO_INITDB_ROOT_USERNAME=monogodb -e MONGO_INITDB_ROOT_PASSWORD=secret mongo
```

Para poder acceder a la consola interactiva y correr comandos de mongo, se ejecuta el siguiente script: 

```
docker exec -it mongodb bash
```





### Resultados

### Conclusión
