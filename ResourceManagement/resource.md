### Resource Management

Docker Flag       Meaning                   Unit              Example
--cpus=0.7 | Limit total CPU usage | Number of CPUs | 0.7 = 70% of 1 CPU
--cpu-shares=1024 | Relative CPU priority | Shares (unitless) | Default = 1024, higher = more
--cpuset-cpus=0,2 | Restrict to specific CPU cores | CPU core indexes | 0,2 = use only cores 0 and 2
--cpu-period=20000 | Length of one CPU allocation cycle | Microseconds (µs) | 20000 µs = 20 ms
--cpu-quota=1000 | Max time container can run in each cpu-period | Microseconds (µs) | 1000 µs = 1 ms = 5% of 20 ms
