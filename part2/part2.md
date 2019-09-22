# 2.1
[docker-compose.yml](./2-1/docker-compose.yml)
```console
➜  2-1 git:(master) ✗ dc up
[sudo] password for kopio: 
Creating network "2-1_default" with the default driver
Creating logger-container ... done
Attaching to logger-container
logger-container | (node:1) ExperimentalWarning: The fs.promises API is experimental
logger-container | Wrote to file /usr/app/logs.txt
logger-container | Wrote to file /usr/app/logs.txt
logger-container | Wrote to file /usr/app/logs.txt
^CGracefully stopping... (press Ctrl+C again to force)
Stopping logger-container ... done

➜  2-1 git:(master) ✗ cat logs.txt 
Tue, 03 Sep 2019 11:05:58 GMT
Tue, 03 Sep 2019 11:06:01 GMT
Tue, 03 Sep 2019 11:06:04 GMT
```

# 2.2
[docker-compose.yml](./2-2/docker-compose.yml)
```console
➜  2-2 git:(master) ✗ dc up
Creating 2-2_web_1 ... done
Attaching to 2-2_web_1
web_1  | 
web_1  | > ports_exercise@1.0.0 start /usr/app
web_1  | > node index.js
web_1  | 
web_1  | Listening on port 80, this means inside of the container. Use -p to map the port to a port of your local machine.

➜  2-2 git:(master) ✗ curl localhost:8000
Ports configured correctly!!
```

# 2.3
[docker-compose.yml](./2-3_2-5_2-6/docker-compose.yml)

# 2.4
```console
➜  scaling-exercise git:(master) dc up --scale compute=3
```

# 2.5
[docker-compose.yml](./2-3_2-5_2-6/docker-compose.yml)

# 2.6
[docker-compose.yml](./2-3_2-5_2-6/docker-compose.yml)

# 2.7
[docker-compose.yml](./2-7/docker-compose.yml)

# 2.8 ja 2.10
[docker-compose.yml](./2-8/docker-compose.yml)
