### Introducción

Este repositorio contiene ejemplo de como levantar contenedores con **Dockerfiles** del siguiente servicio:

* Mongo

### Requerimientos

Para poder levantar estos servicios, debe tener instalado el servicio de [Docker](https://docs.docker.com/get-docker/).



##### Mongo

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
