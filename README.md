# Docker Template for PHP application

A default Dockerfile and docker-compose for quick deployment of the environment for PHP application.

- PHP 8.2
- Nginx
- Postgresql
- Elasticsearch
- docker compose

## Project structure
```
.
├── docker
│   ├── nginx
│   │   ├── default.conf
│   │   ├── Dockerfile
│   │   └── nginx.conf
│   ├── php-fpm
│   │   └── Dockerfile
│   └── postgres
│       └── Dockerfile
├── docker-compose.yml
└── README.md
```


## Installing the Template
```
git clone https://github.com/BlackSou/docker-php-template.git
```

## Building the Docker image for your application
```
docker-compose build
```
### Other commands 
```
docker-compose up -d
```
```
docker-compose start
```
```
docker-compose stop
```
```
docker-compose ps
```
```
docker-compose logs -f
```
```
docker-compose rm
```
```
docker-compose exec -ti php-fpm bash
```