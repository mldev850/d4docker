# Docker Networking: DNS Round Robin Practical Demo

Welcome! In this blog, we'll go step-by-step through a Docker networking practical where we'll create containers, set up DNS round-robin, and test simple load balancing.

---

## What We'll Cover

- Create a custom Docker network
- Create multiple containers with the same network alias
- Test DNS round robin
- Understand why errors happen (and fix them)
- Best practices

---

# Step 1: Create a New Virtual Network

```bash
docker network create mynetwork
```

- This creates a custom **bridge** network named `mynetwork`.
- Containers on the same network can talk to each other using container names and aliases.

---

# Step 2: Create Two Containers with the Same Alias

```bash
docker run -d --network mynetwork --network-alias search bretfisher/httpenv

docker run -d --network mynetwork --network-alias search bretfisher/httpenv
```

- We launch two containers.
- Both have the network alias `search`.
- The `bretfisher/httpenv` image runs a web server on port 8888.

---

# Step 3: Test DNS with `nslookup`

```bash
docker run --rm --net mynetwork alpine nslookup search
```

- Runs a temporary Alpine container.
- Queries DNS for `search`.
- ✅ You should see **two IP addresses**, one for each container.

---

# Step 4: Test with `curl`

If you run this with a minimal image like `centos`, it will fail because CentOS does not have `curl` installed!

### Solution 1: Use Alpine (install curl quickly)

```bash
docker run --rm --net mynetwork alpine sh -c "apk add --no-cache curl && curl -s search:8888"
```

### Solution 2: Use a Dedicated Curl Image

```bash
docker run --rm --net mynetwork curlimages/curl search:8888
```

✅ This is faster because the `curlimages/curl` image already has `curl` preinstalled.

### What You'll See:

- JSON output from the web server.
- If you run the command multiple times, you'll see responses coming from different containers (load balancing behavior).

---

# Why "Error Response from Daemon" Happens?

If you tried:

```bash
docker run --rm --net mynetwork centos curl -s search:8888
```

and saw an error:

> `error response from daemon: OCI runtime create failed: ...: executable file not found in $PATH: unknown`

It's because:

- The `centos` image **does not have curl installed**.
- You must install curl first or use a better image.

---

# DNS Round Robin in Docker: Why Useful?

## Purpose

- **Simple Load Balancing**: Distributes requests across multiple containers.
- **Service Discovery**: All instances reachable via one name.
- **High Availability**: If one container fails, others can still respond.

## Use Cases

- Development and Testing environments.
- Simple microservices architecture.
- Quick web farms.
- Service redundancy without complex tools.

## Limitations

- No health checks (dead containers still show up).
- Simple round-robin only (not smart load balancing).
- DNS client caching may affect effectiveness.

---

# Best Practices

- Use this technique for **simple setups**.
- For production, prefer **Docker Swarm**, **Kubernetes**, or **external load balancers**.
- Add health checks inside your applications.
- Understand how your clients cache DNS entries.

---

# Quick Commands Summary

| Task                              | Command                                                  |
|-----------------------------------|----------------------------------------------------------|
| Create network                    | `docker network create mynetwork`                       |
| Create container with alias       | `docker run -d --network mynetwork --network-alias search bretfisher/httpenv` |
| Test DNS                          | `docker run --rm --net mynetwork alpine nslookup search` |
| Test with curl (using curl image)  | `docker run --rm --net mynetwork curlimages/curl search:8888` |

---

# Bonus Tip: Stopping All Running Containers

If you want to stop all containers quickly:

```bash
docker stop $(docker ps -q)
```

✅ Note: Always use `$(docker ps -q)`, not `${docker ps -q}`.

---

# Conclusion

Docker's built-in DNS round robin is a super useful, lightweight way to achieve basic load balancing and service discovery without any external tools. Now you know how to set it up, troubleshoot errors, and apply best practices!

---

# 🚀 Happy Dockering!

Feel free to share or fork this guide if it helped! 🙌
