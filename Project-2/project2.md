# 🐳 Deep Dive into Docker Images

---

## 📌 Important Concepts

- 🔍 **Image History**
  ```bash
  docker history <image_name>

    View each layer of the image.

    Understand how different instructions affect image size.

    Useful for caching insights.

    📦 Build Context

        The context (usually .) is sent to the Docker daemon during build.

        Be cautious: large contexts slow down builds.

    🚫 .dockerignore File

        Exclude unnecessary files from the build context.

        Works like .gitignore.

    🔍 Inspect Image Contents

    docker run --rm -it <image-id> sh

        Launch a temporary shell to verify ignored files.

        --rm ensures container is cleaned up after exit.

🧹 Docker Cleanup Commands

    🔥 Kill all running containers:

docker kill $(docker ps -q)

🧼 Remove all Docker images:

    docker rmi $(docker images -q)

🌍 Managing Environments
🧾 Way 1: Dockerfile

ENV PORT=5000

📌 This sets environment variables inside the image.
💻 Way 2: CLI Override

docker run -e PORT=8000 -e APP_NAME='oops' -p 8088:8000 <image_id>

✅ This overrides Dockerfile environment variables at runtime.
📂 Way 3: Use .env File

docker run --env-file '.env.prod' -d -p 8085:8000 <image-name>

🎯 Ideal for managing multiple environmen

  
