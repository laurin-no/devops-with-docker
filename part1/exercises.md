# Exercise Solutions Part 1

## Exercise 1.1

```
❯ docker ps -a     
CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS                     PORTS     NAMES
a8472c73207b   nginx     "/docker-entrypoint.…"   27 seconds ago       Exited (0) 2 seconds ago             keen_albattani
146a8dd4152b   nginx     "/docker-entrypoint.…"   30 seconds ago       Exited (0) 2 seconds ago             admiring_torvalds
db9f3eaf9c17   nginx     "/docker-entrypoint.…"   About a minute ago   Up About a minute          80/tcp    serene_chatelet
```

## Exercise 1.2

```
❯ docker ps -a                
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

```

```
❯ docker images               
REPOSITORY   TAG       IMAGE ID   CREATED   SIZE

```

## Exercise 1.3

```
❯ docker run -d --rm -it --name looper-it devopsdockeruh/simple-web-service:ubuntu
❯ docker exec -it looper-it bash
root@0e529c73e2e5:/usr/src/app# tail -f ./text.log
```

> Secret message is: 'You can find the source code here: https://github.com/docker-hy'

## Exercise 1.4

```
❯ docker run --rm -it --name looper-it ubuntu sh -c 'while true; do echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website; done' 
❯ docker exec -it looper-it bash
root@71905af92a10:/# apt update
root@71905af92a10:/# apt install curl
```

## Exercise 1.5

```
❯ docker images
REPOSITORY                          TAG       IMAGE ID       CREATED       SIZE
ubuntu                              latest    3f5ef9003cef   3 weeks ago   69.2MB
devopsdockeruh/simple-web-service   ubuntu    4e3362e907d5   2 years ago   83MB
devopsdockeruh/simple-web-service   alpine    fd312adc88e0   2 years ago   15.7MB

❯ docker run -d --rm -it --name looper-it devopsdockeruh/simple-web-service:alpine
❯ docker exec -it looper-it sh
/usr/src/app # tail -f ./text.log
```

> Secret message is: 'You can find the source code here: https://github.com/docker-hy'

## Exerciese 1.6

```
❯ docker run -it devopsdockeruh/pull_exercise
Unable to find image 'devopsdockeruh/pull_exercise:latest' locally
latest: Pulling from devopsdockeruh/pull_exercise
8e402f1a9c57: Pull complete 
5e2195587d10: Pull complete 
6f595b2fc66d: Pull complete 
165f32bf4e94: Pull complete 
67c4f504c224: Pull complete 
Digest: sha256:7c0635934049afb9ca0481fb6a58b16100f990a0d62c8665b9cfb5c9ada8a99f
Status: Downloaded newer image for devopsdockeruh/pull_exercise:latest
WARNING: The requested image's platform (linux/amd64) does not match the detected host platform (linux/arm64/v8) and no specific platform was requested
Give me the password: basics
You found the correct password. Secret message is:
"This is the secret message"
```

## Exercise 1.7

see `Dockerfile-17`

```
❯ docker build . -t curler
❯ docker run -it curler
```

## Exercise 1.8

see `Dockerfile-18`

```
❯ docker build . -t web-server
❯ docker run web-server
```

## Exercise 1.9

```
❯ touch text.log
❯ docker run -v "$(pwd)/text.log:/usr/src/app/text.log" devopsdockeruh/simple-web-service
```

## Exercise 1.10

```
❯ docker run -p 8080:8080 web-server
```