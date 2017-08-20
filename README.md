[![Build Status](https://travis-ci.org/phenompeople/apache-storm.svg?branch=master)](https://travis-ci.org/phenompeople/apache-storm)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

Dockerfiles for building a storm cluster.

The images are available directly from [phenompeople organization] (https://hub.docker.com/u/phenompeople/)


## **apache-storm**

[![Docker Automated build](https://img.shields.io/docker/automated/phenompeople/apache-storm.svg?style=plastic)](https://hub.docker.com/r/phenompeople/apache-storm/)
[![Docker Build Status](https://img.shields.io/docker/build/phenompeople/apache-storm.svg?style=plastic)](https://hub.docker.com/r/phenompeople/apache-storm/)
[![Docker Pulls](https://img.shields.io/docker/pulls/phenompeople/apache-storm.svg?style=plastic)](https://hub.docker.com/r/phenompeople/apache-storm/)

#### Supported tags

* **`1.1.0` ([apache-storm/1.1.0/Dockerfile](https://bitbucket.org/phenompeople/apache-storm/src/master/apache-storm/1.1.0/Dockerfile))**
* **`1.0.0` ([apache-storm/1.0.0/Dockerfile](https://bitbucket.org/phenompeople/apache-storm/src/master/apache-storm/1.0.0/Dockerfile))**

**NOTE:** `apache-storm` provides only the base images which are build on ONBUILD instructions. The ONBUILD instruction adds to the image a trigger instruction to be executed at a later time, when the image is used as the base for another build.

#### Pre-Requisites

- install docker-engine [https://docs.docker.com/engine/installation/](https://docs.docker.com/engine/installation/)

#### Usage of `onbuild` images

These images can be used to bake your dependencies into an image by extending the plain storm images. To do so, create a custom `Dockerfile` like this:
```dockerfile
FROM phenompeople/apache-storm
```
Don't forget to build that `Dockerfile`:
```
docker build --rm=true -t childimage .
```
```
docker run --rm -t childimage
```

## **storm-ui**

[![Docker Automated build](https://img.shields.io/docker/automated/phenompeople/storm-ui.svg?style=plastic)](https://hub.docker.com/r/phenompeople/storm-ui/)
[![Docker Build Status](https://img.shields.io/docker/build/phenompeople/storm-ui.svg?style=plastic)](https://hub.docker.com/r/phenompeople/storm-ui/)
[![Docker Pulls](https://img.shields.io/docker/pulls/phenompeople/storm-ui.svg?style=plastic)](https://hub.docker.com/r/phenompeople/storm-ui/)

### Supported tags

* **`1.1.0` ([storm-ui/1.1.0/Dockerfile](https://bitbucket.org/phenompeople/apache-storm/src/master/storm-ui/1.1.0))**
* **`1.0.0` ([storm-ui/1.0.0/Dockerfile](https://bitbucket.org/phenompeople/apache-storm/src/master/storm-ui/1.0.0))**

### Pre-Requisites

- install docker-engine [https://docs.docker.com/engine/installation/](https://docs.docker.com/engine/installation/)
- Create storm configuration file based on your requirement, and mount holding directory as a volume during container run time under /opt/storm/conf
  
### How to use this image 

1. This image was build based phenompeople/apache-storm 
1. This image can be used by simply running 

```$ docker run --name=storm-ui -p 8080:8080 -v `pwd`/conf:/opt/storm/conf -td phenompeople/storm-ui```

1. To make image run even after reboot use extra option --restart=always

```$ docker run --restart=always --name=storm-ui -p 8080:8080 -v `pwd`/conf:/opt/storm/conf -td phenompeople/storm-ui```

**Note:** Storm UI expects storm nimbus to be identified by hostname, in order to match hostname with host add optional -h option during run time     

## **storm-nimbus**

[![Docker Automated build](https://img.shields.io/docker/automated/phenompeople/storm-nimubs.svg?style=plastic)](https://hub.docker.com/r/phenompeople/storm-nimbus/)
[![Docker Build Status](https://img.shields.io/docker/build/phenompeople/storm-nimbus.svg?style=plastic)](https://hub.docker.com/r/phenompeople/storm-nimbus/)
[![Docker Pulls](https://img.shields.io/docker/pulls/phenompeople/storm-nimbus.svg?style=plastic)](https://hub.docker.com/r/phenompeople/storm-nimbus/)

### Supported tags

* **`1.1.0` ([storm-nimbus/1.1.0/Dockerfile](https://bitbucket.org/phenompeople/apache-storm/src/master/storm-nimbus/1.1.0))**
* **`1.0.0` ([storm-nimbus/1.0.0/Dockerfile](https://bitbucket.org/phenompeople/apache-storm/src/master/storm-nimbus/1.0.0))**

### Pre-Requisites

- install docker-engine [https://docs.docker.com/engine/installation/](https://docs.docker.com/engine/installation/)
- Create storm configuration file based on your requirement, and mount holding directory as a volume during container run time under /opt/storm/conf
  
### How to use this image 

1. This image was build based phenompeople/apache-storm 
1. This image can be used by simply running 

```$ docker run --name=storm-nimbus -p 6627:6627 -v `pwd`/conf:/opt/storm/conf -td phenompeople/storm-nimbus```

1. To make image run even after reboot use extra option --restart=always

```$ docker run --restart=always --name=storm-nimbus -p 6627:6627 -v `pwd`/conf:/opt/storm/conf -td phenompeople/storm-nimbus```

**Note:** Storm UI expects storm nimbus to be identified by hostname, in order to match hostname with host add optional -h option during run time     

##**storm-supervisor**

[![Docker Automated build](https://img.shields.io/docker/automated/phenompeople/storm-supervisor.svg?style=plastic)](https://hub.docker.com/r/phenompeople/storm-supervisor/)
[![Docker Build Status](https://img.shields.io/docker/build/phenompeople/storm-supervisor.svg?style=plastic)](https://hub.docker.com/r/phenompeople/storm-supervisor/)
[![Docker Pulls](https://img.shields.io/docker/pulls/phenompeople/storm-supervisor.svg?style=plastic)](https://hub.docker.com/r/phenompeople/storm-supervisor/)

### Supported tags

* **`1.1.0` ([storm-supervisor/1.1.0/Dockerfile](https://bitbucket.org/phenompeople/apache-storm/src/master/storm-supervisor/1.1.0))**
* **`1.0.0` ([storm-supervisor/1.0.0/Dockerfile](https://bitbucket.org/phenompeople/apache-storm/src/master/storm-supervisor/1.0.0))**

### Pre-Requisites

- install docker-engine [https://docs.docker.com/engine/installation/](https://docs.docker.com/engine/installation/)
- Create storm configuration file based on your requirement, and mount holding directory as a volume during container run time under /opt/storm/conf

**Note:** Storm supervisor ports were defined in image between 6700 to 6710 port. Please update your configuration file accordingly    

### How to use this image 

1. This image was build based phenompeople/apache-storm 
1. This image can be used by simply running 

```$ docker run --name=storm-supervisor -v `pwd`/conf:/opt/storm/conf -td phenompeople/storm-supervisor```

1. To make image run even after reboot use extra option --restart=always

```$ docker run --restart=always --name=supervisor -v `pwd`/conf:/opt/storm/conf -td phenompeople/storm-supervisor```

## Maintainers

* Rajesh Jonnalagadda (<rajesh.jonnalagadda@phenompeople.com>)

## License and Authors

License	::		Apache License

Author		::		Phenompeople Pvt Ltd (<admin.squad@phenompeople.com>)