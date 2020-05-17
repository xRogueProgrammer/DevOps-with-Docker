# DevOps-with-Docker
DevOps Course from Helsinki &amp; eficode

# Part 1

## Exercise 1.1

``` 
~$ docker ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS                      PORTS               NAMES
09f3f61a4207        nginx               "nginx -g 'daemon of…"   3 minutes ago       Exited (0) 14 seconds ago                       intelligent_mcclintock
7f602edf7e46        nginx               "nginx -g 'daemon of…"   3 minutes ago       Exited (0) 6 seconds ago                        pensive_brown
da1db3cdd718        nginx               "nginx -g 'daemon of…"   4 minutes ago       Up 3 minutes                80/tcp              wizardly_galileo
```

## Exercise 1.2

``` 
~$ docker ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES

~$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
```

## Exercise 1.3

``` 
~$ docker run -it devopsdockeruh/pull_exercise
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

## Exercise 1.4

```
~$ docker run devopsdockeruh/exec_bash_exercise
(node:1) ExperimentalWarning: The fs.promises API is experimental
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt
Wrote to file /usr/app/logs.txt

~$ docker exec -it objective_visvesvaraya bash
root@7d4f6e515591:/usr/app# ps aux
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root         1  0.1  0.2 592596 30008 ?        Ssl  21:01   0:00 node index
root        16  3.5  0.0  18188  3168 pts/0    Ss   21:04   0:00 bash
root        21  0.0  0.0  36636  2808 pts/0    R+   21:04   0:00 ps aux
root@7d4f6e515591:/usr/app# tail -f ./logs.txt
Mon, 20 Apr 2020 21:04:19 GMT
Secret message is:
"Docker is easy"
Mon, 20 Apr 2020 21:04:25 GMT
Mon, 20 Apr 2020 21:04:28 GMT
Mon, 20 Apr 2020 21:04:31 GMT
Mon, 20 Apr 2020 21:04:34 GMT
Secret message is:
"Docker is easy"
Mon, 20 Apr 2020 21:04:40 GMT
Mon, 20 Apr 2020 21:04:43 GMT
Mon, 20 Apr 2020 21:04:46 GMT
Mon, 20 Apr 2020 21:04:49 GMT
^C
```

## Exercise 1.5
```
~$ docker run -d --name ubuntu_web ubuntu:18.04 sh -c 'while true; do date; sleep 1; done'
Unable to find image 'ubuntu:18.04' locally
18.04: Pulling from library/ubuntu
5bed26d33875: Pull complete 
f11b29a9c730: Pull complete 
930bda195c84: Pull complete 
78bf9a5ad49e: Pull complete 
Digest: sha256:bec5a2727be7fff3d308193cfde3491f8fba1a2ba392b7546b43a051853a341d
Status: Downloaded newer image for ubuntu:18.04
13a71ecac44f1941c7ed848342b09912c4c790ff8bddcf3491e50ef1deaa984d

~$ docker logs -f ubuntu_web
Wed Apr 22 02:49:49 UTC 2020
Wed Apr 22 02:49:50 UTC 2020
Wed Apr 22 02:49:51 UTC 2020
Wed Apr 22 02:49:52 UTC 2020

~$ docker exec -it ubuntu_web bash

root@13a71ecac44f:/# apt-get update; apt-get install curl


~$ sh -c 'echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;'
Input website:
helsinki.fi
Searching..
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="http://www.helsinki.fi/">here</a>.</p>
</body></html>
```

## Exercise 1.6
```
~$ docker build -t docker-clock .
Sending build context to Docker daemon  2.048kB
Step 1/1 : FROM devopsdockeruh/overwrite_cmd_exercise
latest: Pulling from devopsdockeruh/overwrite_cmd_exercise
092586df9206: Pull complete 
ef599477fae0: Pull complete 
4530c6472b5d: Pull complete 
d34d61487075: Pull complete 
87fc2710b63f: Pull complete 
e83c771c5387: Pull complete 
fef6195892ae: Pull complete 
70e1a68db517: Pull complete 
c2599bbef3cb: Pull complete 
c5a7dd6f6ae1: Pull complete 
446220381e79: Pull complete 
27d5280e809c: Pull complete 
Digest: sha256:02e38f4285d5cfaff5ed57ae67a8d99e041027da8f5c972329b46e2b7a47b7d2
Status: Downloaded newer image for devopsdockeruh/overwrite_cmd_exercise:latest
 ---> 3d2b622b1849
Successfully built 3d2b622b1849
Successfully tagged docker-clock:latest

~$ docker run docker-clock

-h,       	--help           	to show this message
-a [age], 	--adult [age]    	to check if you're older than 18
-c [time],	--clock [time]   	to start a clock
-t [size],	--triangle [size]	to draw a triangle, takes second argument as the size
    
~$ docker run docker-clock -c 0
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
```
