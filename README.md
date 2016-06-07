# Demo for use of a Nginx Reverse Proxy container with Docker

The main part here is the reverse proxy image by Jason Wilder: https://github.com/jwilder/nginx-proxy

In order to test:

* Start the proxy

```
docker run -d -p 80:80 -v /var/run/docker.sock:/tmp/docker.sock -t jwilder/nginx-proxy
```

* Run the `project-a` container

```
cd project-a && docker-compose up -d
```

* Run the `project-b` container

```
cd project-b && docker-compose up -d
```

* Add hosts entries

```
127.0.0.1 project-a
127.0.0.1 project-b
```
