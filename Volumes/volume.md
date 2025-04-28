### History
- The data or any file content inside that container by default is restricted to that container only in it's lifecycle.

### Volumes
 - Persisting data beyond the container's lifecycle
### Bind Mount
 - docker run --rm -d -p 3000:3000 -v ./src:/app/src -v ./public:/app/public reactapp:v0 
 - source : Destination
 - Host filesystem : container filesystem

### Named Volumes
 -  docker volume create my-volume
 - docker run -d -p 8080:80 --name web-server1 -v my-volume:/usr/share/nginx/html  nginx:1.27.0
 - docker run -d -p 8081:80  --name web-server2 -v my-volume:/usr/share/nginx/html nginx:1.27.0
 - docker run -d -p 8082:80  --name web-server3 -v my-volume:/usr/share/nginx/html nginx:1.27.0

- Changes are reflected across all the containers with same named volumes.

###  Managing Volumes with CLI
- docker volume ls
- docker volume create <VOLUME_NAME>
- docker inspect volume <VOLUME_NAME>
- docker volume ls -f dangling=true ( Dangling not being used by any containers )


 
 
