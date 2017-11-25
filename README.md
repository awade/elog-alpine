# elog-alpine
Implementation of The Elog in an Alpine based docker.

This Dockerfile creates a docker image of an elog server (https://midas.psi.ch/elog/) built on Alpine linux (https://alpinelinux.org/).

The idea is to build the lightest possible deployment so that it may be run on a lab computer with many other common tools: i.e. to have the least possible overhead.

A number of other docker builds use Ubuntu and Debian, and, therefore contain a lot of unnecessary stuff. This is an attempt to make it as small as possible with all config and data stored in an mounted volume external to the container.

## Building the docker image locally
Pull docker from github with
```
git clone --recursive git://github.com/fincle/elog-alpine.git
cd ./elog-alpine
```

You can modify the elogd.cfg file if you like, or not, and then build
```
docker build -t elog .
```

You can also get the images directly from docker, useful if you want to deploy directly

```
docker pull fincle/elog-alpine
```

To run the docker image on local machine
```
docker run -p 8080:8080 --mount source=my-vol,target=/home elog:latest
```

Here my-vol is a docker defined volume, this can be made with 
```
docker volume create my-vol
```
or by any other way you make/mount a volue to docker.

You can then access from a browser at http://localhost:8080
