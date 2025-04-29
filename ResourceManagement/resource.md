### Resource Management
- --cpus=0.7
    Limit the container to use at most 70% of a single CPU core.

- --cpu-shares=1024
    Set the container’s CPU priority relative to others. Higher cpu-shares means the container gets more CPU time when the system is under load (default is 1024).

-  --cpuset-cpus=0,2
    Restrict the container to run only on specific CPU cores (in this case, CPU 0 and CPU 2).

-    --cpu-period=20000 and --cpu-quota=1000
    Control how much CPU time the container gets.
    cpu-period defines the length of one scheduling cycle (in microseconds).

-   cpu-quota sets the maximum time (also in microseconds) the container can use CPU in each cycle.
        (For example, quota 1000 over a period 20000 means the container can use 5% CPU.)

