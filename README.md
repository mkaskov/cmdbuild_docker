# CMDBuild docker
Docker CMDBuild 2.5 with Shark Workflow


## Clone repository

``` bash
git clone https://github.com/mkaskov/cmdbuild_docker.git
```

## Build and run docker containers

``` bash
cd cmdbuild_docker

docker network create network1

docker build dockerfile_cmdbuild/ -t cmdbuild_tomcat
docker run --name cmdbuild_tomcat --net=network1 -p 8080:8080 -d cmdbuild_tomcat

docker run --name cmdbuild_postgres --net=network1 -e POSTGRES_PASSWORD=YOUR_POSTGRES_PASSWORD -p 55432:5432 -d postgres:9.3
```

Then open http://localhost:8080/cmdbuild/ and configure cmdbuild app


## Database configuration

- Host: cmdbuild_postgres
- Port: 5432
- Username: postgres 
- Password: YOUR_POSTGRES_PASSWORD


After finish configuration cmdbuild app and swith-on workflow in admin menu you need to restart docker with tomcat 

``` bash
docker restart cmdbuild_tomcat
```


## pgAdmin4 docker

Optionally you can use pgAdmin4 docker:

``` bash
docker run --name pgadmin4 --net=network1 -p 5050:5050 -d thajeztah/pgadmin4
```

After that you can open pgAdmin4 http://localhost:5050

## Wiki

[autostart containers with systemd](https://github.com/mkaskov/cmdbuild_docker/wiki/autostart-containers-with-systemd)  
[Docker & DB commands](https://github.com/mkaskov/cmdbuild_docker/wiki/Docker-&-DB-commands)  

