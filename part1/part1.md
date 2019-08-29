# 1.1
```console
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course$ d run -d nginx
Unable to find image 'nginx:latest' locally
latest: Pulling from library/nginx
1ab2bdfe9778: Pull complete 
a17e64cfe253: Pull complete 
e1288088c7a8: Pull complete 
Digest: sha256:53ddb41e46de3d63376579acf46f9a41a8d7de33645db47a486de9769201fec9
Status: Downloaded newer image for nginx:latest
6ea6846fb4f4c5547bdaadacb69d0f91eedf262c653bea07187ee4d010712878
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course$ d run -d nginx
5dc8d4aba85b41420a4986ed6bb1916145646af8b9f0c8896e7632c6c2ef23e2
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course$ d run -d nginx
1e2580305afcd471d083eb86e360265e1a739b8be5c91de3fba215c84b76abe0
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course$ d ps
CONTAINER ID        IMAGE               COMMAND                  CREATED              STATUS              PORTS               NAMES
1e2580305afc        nginx               "nginx -g 'daemon of…"   4 seconds ago        Up 2 seconds        80/tcp              determined_sinoussi
5dc8d4aba85b        nginx               "nginx -g 'daemon of…"   About a minute ago   Up About a minute   80/tcp              amazing_thompson
6ea6846fb4f4        nginx               "nginx -g 'daemon of…"   About a minute ago   Up About a minute   80/tcp              laughing_archimedes
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course$ d stop 1e 5d
1e
5d
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course$ d ps -a
CONTAINER ID        IMAGE               COMMAND                  CREATED              STATUS                      PORTS               NAMES
1e2580305afc        nginx               "nginx -g 'daemon of…"   About a minute ago   Exited (0) 25 seconds ago                       determined_sinoussi
5dc8d4aba85b        nginx               "nginx -g 'daemon of…"   2 minutes ago        Exited (0) 25 seconds ago                       amazing_thompson
6ea6846fb4f4        nginx               "nginx -g 'daemon of…"   2 minutes ago        Up 2 minutes                80/tcp              laughing_archimedes
```

# 1.2
```console
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course$ d stop 6
6
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course$ d container prune
WARNING! This will remove all stopped containers.
Are you sure you want to continue? [y/N] y
Deleted Containers:
1e2580305afcd471d083eb86e360265e1a739b8be5c91de3fba215c84b76abe0
5dc8d4aba85b41420a4986ed6bb1916145646af8b9f0c8896e7632c6c2ef23e2
6ea6846fb4f4c5547bdaadacb69d0f91eedf262c653bea07187ee4d010712878

Total reclaimed space: 0B
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course$ d ps -a
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course$ d system prune
WARNING! This will remove:
        - all stopped containers
        - all networks not used by at least one container
        - all dangling images
        - all build cache
Are you sure you want to continue? [y/N] y
Deleted Images:
# Many
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course$ d images
# Some personal stuff left
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course$ d rmi -f 5a 50 fc 35
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course$ d images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
```

# 1.3
```console
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course$ docker run -it devopsdockeruh/pull_exercise
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

# 1.4
```console
kopio@kopio-ThinkPad-T450s:~$ docker run -d --name container devopsdockeruh/exec_bash_exercise
Unable to find image 'devopsdockeruh/exec_bash_exercise:latest' locally
latest: Pulling from devopsdockeruh/exec_bash_exercise
741437d97401: Pull complete 
34d8874714d7: Pull complete 
0a108aa26679: Pull complete 
7f0334c36886: Pull complete 
65c95cb8b3be: Pull complete 
a36b708560f8: Pull complete 
4090f912e6c7: Pull complete 
ce5fe2607c2e: Pull complete 
9400f5f657d6: Pull complete 
c4919883f7fa: Pull complete 
Digest: sha256:c463832132d1fb0b8b3b60348a6fc36fda7512a4ef2d1050e8bea7b6a6d7a2f3
Status: Downloaded newer image for devopsdockeruh/exec_bash_exercise:latest
8b7b4ae55c1884dde187e9b6a1a54c027b6d490f8fe7924100b595a6196a1618
kopio@kopio-ThinkPad-T450s:~$ docker exec -it container bash
root@8b7b4ae55c18:/usr/app# tail -f ./logs.txt
"Docker is easy"
Thu, 22 Aug 2019 13:05:03 GMT
Thu, 22 Aug 2019 13:05:06 GMT
Thu, 22 Aug 2019 13:05:09 GMT
Thu, 22 Aug 2019 13:05:12 GMT
Secret message is:
"Docker is easy"
```

# 1.5
```console
docker run -it --name web ubuntu sh -c 'echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;'
Input website:
```
In another terminal:
```console
docker exec -it web bash
apt update
apt install curl
```
In the first terminal:
```console
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

# 1.6
[Dockerfile](./1-6/Dockerfile)

Finding the correct command:
```console
docker run devopsdockeruh/overwrite_cmd_exercise
docker run devopsdockeruh/overwrite_cmd_exercise -c
```
Building and running:
```console
docker build -t clock .
docker run clock
1
2
3
# ...
```

# 1.7
[Files](./1.7)
```console
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course/part1/1-7$ docker build -t curler .
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course/part1/1-7$ docker run -it curler
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

# 1.8
```console
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course/part1$ touch logs.txt
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course/part1$ sudo docker run -v $(pwd)/logs.txt:/usr/app/logs.txt devopsdockeruh/first_volume_exercise
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course/part1$ cat logs.txt 
Fri, 23 Aug 2019 14:33:46 GMT
Fri, 23 Aug 2019 14:33:49 GMT
Fri, 23 Aug 2019 14:33:52 GMT
Fri, 23 Aug 2019 14:33:55 GMT
Secret message is:
"Volume bind mount is easy"
Fri, 23 Aug 2019 14:34:01 GMT
Fri, 23 Aug 2019 14:34:04 GMT
```

# 1.9
```console
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course/part1$ docker run -p 8080:80 devopsdockeruh/ports_exercise
kopio@kopio-ThinkPad-T450s:~$ curl localhost:8080
Ports configured correctly!!
```

# 1.10
[Dockerfile](./1-10/frontend-example-docker/Dockerfile)

# 1.11
[Dockerfile](./1-11/backend-example-docker/Dockerfile)
```console
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course/part1/1-11/backend-example-docker$ docker build -t node-backend .
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course/part1/1-11/backend-example-docker$ docker run -p 8000:8000 -v $(pwd)/logs.txt:/app/logs.txt node-backend
```

# 1.12
[Frontend Dockerfile](./1-10/frontend-example-docker/Dockerfile)
[Backend Dockerfile](./1-11/backend-example-docker/Dockerfile)
```console
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course/part1/1-11/backend-example-docker$ docker run -p 8000:8000 -v $(pwd)/logs.txt:/app/logs.txt node-backend
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course/part1/1-10/frontend-example-docker$ docker run -p 5000:5000 node-container
```

# 1.13
[Dockerfile](./1-13/spring-example-project/Dockerfile)
```console
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course/part1/1-13/spring-example-project$ docker build -t spring-example-project .
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course/part1/1-13/spring-example-project$ docker run -p 8080:8080 spring-example-project
```

# 1.14
[Dockerfile](./1-14/rails-example-project/Dockerfile)
```console
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course/part1/1-13/rails-example-project$ docker build -t rails-example-project .
kopio@kopio-ThinkPad-T450s:~/git/yliopisto/docker-course/part1/1-13/rails-example-project$ docker run -p 3000:3000 rails-example-project
```

# 1.15
Python-template:
[Github](https://github.com/osakunta/python-template),
[Docker Hub](https://cloud.docker.com/u/osakunta/repository/docker/osakunta/python-template)

Run the container with:
```console
docker run osakunta/python-template
```

# 1.16
[Heroku app](https://docker-course.herokuapp.com/)
