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
