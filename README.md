# DevOps-with-Docker
DevOps Course from Helsinki &amp; eficode

# Part 1

## Exercise 1.1

``` ~$ docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                      PORTS               NAMES
09f3f61a4207        nginx               "nginx -g 'daemon of…"   3 minutes ago       Exited (0) 14 seconds ago                       intelligent_mcclintock
7f602edf7e46        nginx               "nginx -g 'daemon of…"   3 minutes ago       Exited (0) 6 seconds ago                        pensive_brown
da1db3cdd718        nginx               "nginx -g 'daemon of…"   4 minutes ago       Up 3 minutes                80/tcp              wizardly_galileo
```

## Exercise 1.2

``` ~$ docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES

~$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
```

## Exercise 1.3

``` ~$ docker run -it devopsdockeruh/pull_exercise
Unable to find image 'devopsdockeruh/pull_exercise:latest' locally
latest: Pulling from devopsdockeruh/pull_exercise
8e402f1a9c57: Pull complete 
5e2195587d10: Pull complete 
6f595b2fc66d: Pull complete 
165f32bf4e94: Pull complete 
67c4f504c224: Pull complete 
Digest: sha256:7c0635934049afb9ca0481fb6a58b16100f990a0d62c8665b9cfb5c9ada8a99f
Status: Downloaded newer image for devopsdockeruh/pull_exercise:latest

Give me the password: basics
You found the correct password. Secret message is:
"This is the secret message"

```
