# docker

## make local repository

```ps
docker container run -d -p 5000:5000 --name randomsilo -v G:\shop\randomsilo\docker\registry
```

## docker on rpi

### install docker

```bash
curl -sSL https://get.docker.com | sh
```

### create dockerfile

```bash
# vi Dockerfile
FROM armbuild/debian:latest
RUN apt-get update && apt-get -y install curl php5 && apt-get clean
RUN mkdir -p /shop/randomsilo/web
WORKDIR /shop/randomsilo/web
RUN echo "<h1>Test</h1>" >> /shop/randomsilo/web/index.php
EXPOSE 80
CMD ["php","-S","0.0.0.0:8080"]
```

### buid image

```bash
docker build --rm -f "examples\debian_web\Dockerfile" -t debian_web:latest examples\debian_web
```

### run image

```bash
# run
docker run -d -p 8080:8080 --name test debian_web

# stop
docker stop test

# remove
docker rm test

# run with override directory
docker run -d -p 8080:8080 -v C:/shop/randomsilo/pi-zero-cluster/examples/web/:/shop/randomsilo/web/ --name test debian_web
```

