# CMDBuild docker
docker cmdbuild with shark

## Build
To build:
``` bash
docker build dockerfile_cmdbuild/ -p 8080:8080 -t cmdbuild_max
```

### Starting postgres
docker run --name cmdbuild_postgres -e POSTGRES_PASSWORD=YOUR_POSTGRES_PASSWORD -p 55432:5432 -d postgres:9.3
//docker build postgres:9.3 -t cmdbuild_postgres -p 55432:5432 -d

## Start
To start (need docker-compose):
``` bash
docker-compose up
```
or
``` bash
docker-compose up -d
```
to stop
``` bash
docker-compose down
```

## Database configuration

- Host: pgsql
- Port: 5432
- Username: postgres 
- Password: YOUR_POSTGRES_PASSWORD

## Connection to database with pgAdmin4

``` bash
docker run --rm --net=cmdbuild-network -p 5050:5050 thajeztah/pgadmin4
docker run --net=cmdbuild-network -p 5050:5050 thajeztah/pgadmin4
```

