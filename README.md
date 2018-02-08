# CMDBuild docker
docker cmdbuild 2.5 with shark

Inside a project directory:

``` bash
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


## docker stop|start|restart container

``` bash
docker stop|start|restart <container_name>
```
