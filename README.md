apache-storm
============

Dockerfiles for building a storm cluster.

The images are available directly from [phenompeople](https://hub.docker.com/u/phenompeople/)

##Pre-Requisites

- install docker-engine [https://docs.docker.com/engine/installation/](https://docs.docker.com/engine/installation/)

## Supported tags
* **`1.1.0` ([apache-storm/1.1.0/Dockerfile](https://bitbucket.org/phenompeople/apache-storm/src/master/apache-storm/1.1.0/Dockerfile))**
* **`1.0.0` ([apache-storm/1.0.0/Dockerfile](https://bitbucket.org/phenompeople/apache-storm/src/master/apache-storm/1.0.0/Dockerfile))**

**NOTE:** `apache-storm` provides only the base images which are build on ONBUILD instructions. The ONBUILD instruction adds to the image a trigger instruction to be executed at a later time, when the image is used as the base for another build.

## Usage of `onbuild` images

These images can be used to bake your dependencies into an image by extending the plain storm images. To do so, create a custom `Dockerfile` like this:
```
FROM phenompeople/apache-storm
```
Don't forget to build that `Dockerfile`:
```
docker build --rm=true -t childimage .
docker run --rm -t childimage
```

