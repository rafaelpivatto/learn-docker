## Some docker cli used

### Iterative mode

```
docker container run -p 8080:80 -v //c/Users/rafae/projetos/learn-docker/ex-volume/html:/usr/share/nginx/html nginx
```

### Daemon mode

```
docker container run -d --name ex-daemon-basic -p 8080:80 -v //c/Users/rafae/projetos/learn-docker/ex-volume/html:/usr/share/nginx/html nginx
```

### Stop container

```
docker container stop ex-daemon-basic
```

### Start container

```
docker container start ex-daemon-basic
```

### See container logs

```
docker container logs ex-daemon-basic
```

### Inspect container

```
docker container inspect ex-daemon-basic
```

### To exec command in container

```
docker container exec ex-daemon-basic uname -or
```

### Build with args

```
docker image build --build-arg S3_BUCKET=myapp -t ex-build-arg .
docker container run ex-build-arg bash -c 'echo $S3_BUCKET'
```

### Inspect args

```
docker image inspect --format="{{index .Config.Labels \"maintainer\"}}" ex-build-arg
```

### Build dev

```
docker run -it -v //c/Users/rafae/projetos/learn-docker/build-dev:/app -p 80:8000 ex-build-dev
```

### Prepare tag before push

```
docker image tag ex-simple-build {{hub_username}}/simple-build:1.0
```

### Login and push to hub

```
docker login --username={{hub_username}}
docker image push {{hub_username}}/simple-build:1.0
```
