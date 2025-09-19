To quickly set up and run Redis using Docker Compose, follow these concise steps:

1. **Deploy the Redis service**:

   Open a terminal in the directory containing the `docker-compose.yml` file and execute:

   ```bash
   docker-compose up -d
   ```

2. **Verify the Redis service**:

   Check if the Redis container is running:

   ```bash
   docker ps
   ```

3. **Access the Redis CLI**:

   Connect to the running Redis container:

   ```bash
   docker exec -it $(docker ps -q -f name=redis) redis-cli
   ```

   Alternatively, if you have the Redis CLI installed locally:

   ```bash
   redis-cli -h 127.0.0.1 -p 6379
   ```

4. **Test Redis functionality**:

   Within the Redis CLI, set and retrieve a value:

   ```redis
   SET test "Docker Compose with Redis"
   GET test
   ```

   You should see:

   ```
   "Docker Compose with Redis"
   ```

For a practical walkthrough, consider this tutorial:

[Using Redis with Docker and Docker Compose](https://geshan.com.np/blog/2022/01/redis-docker/)
