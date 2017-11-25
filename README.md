# elog-alpine
Implementation of The Elog in an Alpine based docker.

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
