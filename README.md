# stores

## TLDR

All commands should be run from the makefile. If you don't have make you can copy paste the commads and run them as shell scripts


### Prerequisites

```
docker
docker-compose
make
```



### Usage

```
make setup
```

Installs packages and builds the 3 containers

```
make start
```

Stars up the application on port 3108 

```
make stop
```

Stops the application and stops any linked containers

## Explanation

* Web container runs React. Webpack-dev-server runs dev 
* API container runs Rails
* Nginx reverse proxy between web and api
* No CORS configuration needed, handled by nginx
* All appropriate commands in Makefile

## TROUBLESHOOTING

* 502 Bad Gateway

This may happen if you have gone to the browser before the rails or react apps have finished building. nginx is ready but rails or react isn't. Once application is running this sohuld no longer occur.

* No content.

This will be an issue with the seeds, if any kind of build command has been run twice or not shut down cleanly. For time being this is fixed by running 'make reset'

* Anything missing is because its not done yet!

* More details in the long read
