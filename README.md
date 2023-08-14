# Docker Template for PHP application

A default Dockerfile and docker-compose for quick deployment of the environment for PHP application.

```
.
├── docker
│   ├── nginx
│   │   ├── default.conf
│   │   ├── Dockerfile
│   │   └── nginx.conf
│   ├── php-fpm
│   │   └── Dockerfile
│   └── docker-compose.yml
├── Makefile
└── README.md
```

## Installing the Template
```
git clone https://github.com/BlackSou/docker-php-template.git
```

## Building the Docker image for your application
```
make dc_build
```
Other commands can be found in the Makefile