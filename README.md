**1.- Crear el Dockerfile**

```plaintext
FROM registry.redhat.io/redhat-openjdk-18/openjdk18-openshift
COPY . /deployments/passwordapi
```

**2.- Descargar la imagen del registry de redhat haciendo un user**

Este paso es necesario para poder hacer el build de la imagen, en vista que nos da un error al intentar hacerlo.

docker login registry.redhat.io
Username: lugoea
Password:
Login Succeeded

docker pull registry.redhat.io/redhat-openjdk-18/openjdk18-openshift:1.12-1.1658775370


**2.- Construir la imagen**

```plaintext
    $ docker build -t my-password-api-redhat:1.0.0 .
```

**3.- Correr la imagen**

```plaintext
    $ docker run -it --rm --name running-passwordapi-redhat -p 8080:8080 my-password-api-redhat:1.0.0
```

**4.- Crear el repo en Dockerhub**

elugo/taller-docker-ejercicio6

**5.- Aplicar el tag a la imagen**

```plaintext
    docker tag my-password-api-redhat:1.0.0 elugo/taller-docker-ejercicio6:1.0.0
```

**6.- Hacer Login en docker**

    docker login

    Login with your Docker ID to push and pull images from Docker Hub. If you don't have a Docker ID, head over to https://hub.docker.com to create one.

    Username: elugo

    Password:

    Login Succeeded

  
**7.- Hacer el push a la imagen**

```plaintext
    docker push elugo/taller-docker-ejercicio6:1.0.0
```

**Link**

    https://hub.docker.com/r/elugo/taller-docker-ejercicio6
