### Resource Management
| Docker Flag            | Meaning                                              | Unit                 | Example                           |
|------------------------|------------------------------------------------------|----------------------|------------------------------------|
| `--cpus=0.7`           | Limit total CPU usage                                | Number of CPUs       | `0.7` = 70% of 1 CPU              |
| `--cpu-shares=1024`    | Relative CPU priority                                | Shares (unitless)    | Default = `1024`, higher = more   |
| `--cpuset-cpus=0,2`    | Restrict to specific CPU cores                       | CPU core indexes     | `0,2` = use only cores 0 and 2    |
| `--cpu-period=20000`   | Length of one CPU allocation cycle                   | Microseconds (µs)    | `20000 µs` = 20 ms                |
| `--cpu-quota=1000`     | Max time container can run in each `cpu-period`      | Microseconds (µs)    | `1000 µs` = 1 ms = 5% of 20 ms    |


### Memory
| Docker Flag               | What It Does                                                      | Unit          | Example                      |
|---------------------------|-------------------------------------------------------------------|---------------|-------------------------------|
| `--memory` or `-m`        | Sets the **maximum RAM** the container can use                   | MB / GB       | `-m 512m` = 512 MB, `2g` = 2 GB |
| `--memory-swap`           | Sets **RAM + swap** (extra virtual memory) available             | MB / GB       | If RAM is 1g and swap is 2g → 1g RAM + 1g swap |
| `--memory-reservation`    | A **soft limit** – try to stay under this, okay to go above      | MB / GB       | `300m` means stay under 300 MB if possible |
| `--oom-kill-disable`      | Prevents Docker from **killing the container** if it uses too much memory | true / false  | `--oom-kill-disable=true`     |
| `--memory-swappiness`     | Controls how much memory goes to **swap** (0 = never, 100 = often) | Percent       | `--memory-swappiness=60` (default) |


⚠️ Key rule: --memory overrides in any conflict.
