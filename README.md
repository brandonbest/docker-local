# docker-local
Local Docker Setup with SSL, Nginx-proxy, MySQL, Redis and Postgres

# Performance Improvements
  1. Increase amount of CPU/RAM allocated to Docker
  2. Use `delegated` on volume mounts (https://docs.docker.com/docker-for-mac/osxfs-caching/)
  3. Use a package to optimize refreshing database

## Volume Mounts
```
volumes:
  - ${APP_PATH:-/Users/Brandon/Sites/brandonbest.com}:/app:{cached|delegated}
```
