NOTE: Inspect the containers.

### Without Restart 

docker run -d --name dead  busybox sh -c " sleep 3; exit 1"

### With Restart 

Useful only when containers exit with non-zero.

docker run -d --name restart_aga --restart on-failure busybox sh -c " sleep 3; exit 1"


### Restart these many times

docker run -d --name restart-times --restart on-failure:4  busybox sh -c "sleep 3; exit 1"

###   With any  exit code 

docker run -d --name restart_always  --restart always busybox sh -c "sleep 3; exit 1"


### Restart unless stop

docker run -d --name restart_unless --restart unless-stopped busybox sh -c "sleep 3; exit 0"


--restart always and unless-stopped: Containers will restart automatically.

--restart on-failure: Will not restart after reboot — because it’s not considered a failure


