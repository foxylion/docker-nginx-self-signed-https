# Nginx Proxy with self-signed certificate [![Docker Stars](https://img.shields.io/docker/stars/foxylion/nginx-self-signed-https.svg?style=flat-square)](https://hub.docker.com/r/foxylion/nginx-self-signed-https/) [![Docker Pulls](https://img.shields.io/docker/pulls/foxylion/nginx-self-signed-https.svg?style=flat-square)](https://hub.docker.com/r/foxylion/nginx-self-signed-https/)

This is a small docker image which can be used as a reverse proxy before your
local running service. It acts as a HTTP terminating proxy.

## Usage

```bash
docker run -d --name app-proxy --net host \
           -e REMOTE_URL=http://127.0.0.1:8080 \
           foxylion/nginx-self-signed-https:latest
```

Note: This is running the container on the host network. It is required that
port 80 and 443 are not used by any other application. Also this does only work
when Docker can be ran natively. This won't work on Mac OS X and Windows.
