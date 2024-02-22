# Traning Modernize Day 3

- อธิบายรายละเอียดของ Docker Volume, Docker Compose และการตั้งค่า env

Step
- Postgres [Link](/day3/postgres/README.md)
- docker compose (postgresql, pgadmin, web) [Link](/day3/docker-compose/README.md)
- ตั้งค่า env [Link](/day3/environ/README.md)

Option
- Portainer [Link](https://docs.portainer.io/start/install-ce/server/docker/linux)
```
docker run -d -p 8000:8000 -p 9443:9443 -p 9000:9000 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
```

- RedisInsight [Link](https://redis.com/redis-enterprise/redis-insight/)
```
docker run -v redisinsight:/db -d -p 5540:5540 --name redislnsight redislabs/redisinsight:latest
```

- Redis Stack [Link](https://redis.io/docs/about/about-stack/)
```
docker run -d --name redis-stack -p 6379:6379 -p 8001:8001 redis/redis-stack:latest
```

Other
- https://docs.docker.com/get-started/docker_cheatsheet.pdf
- https://github.com/docker/awesome-compose
- https://blog.tichaky.com/category/docker/
- https://blog.tichaky.com/use-portainer-to-manage-containers/
- https://blog.tichaky.com/lets-get-to-know-volume-on-docker/