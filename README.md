# Docker Nginx Containerisation

Containerised an Nginx web server using Docker and pushed 
the image to Docker Hub.

## What it does

- Builds a custom Nginx image using a two-line Dockerfile
- Serves a static HTML page inside the container
- Image available publicly on Docker Hub

## Dockerfile

```dockerfile
FROM nginx:alpine
COPY index.html /usr/share/nginx/html/index.html
```

## How to run

```bash
# Pull from Docker Hub
docker pull tofik01/my-nginx:v1

# Run the container
docker run -d -p 8080:80 tofik01/my-nginx:v1

# Visit in browser
http://localhost:8080
```

## What I learned

- Docker image layers — only 24.6kB custom layer uploaded, 
  base Nginx layers reused from Docker Hub registry
- Port mapping (-p hostport:containerport)
- Difference between image and container
- docker build, run, stop, rm, push commands

## Docker Hub

Image: docker.io/tofik01/my-nginx:v1
