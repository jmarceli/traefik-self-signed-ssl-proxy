Traefik - proxy development server with self-signed SSL certificate
===

This repository shows an example of a Docker Traefik container configuration that adds a self-signed SSL certificate to a running application server.

A detailed tutorial is available here: https://www.grzegorowski.com/traefik-proxy-development-server-self-signed-ssl/

## Instructions

In [traefik.toml](traefik.toml) file adjust `192.168.0.16` IP address, domain name `my.test` and ports `5000` and `4000` if needed.

Then inside root repository dir execute:

```bash
docker-compose up
```

**NOTE**: If you have changed the domain name `my.test` to any other, you should generate a new self-signed SSL certificate files with:

```bash
openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout cert.key -out cert.crt
```

Execute this command inside `./certs/` dir and enter the correct FQDN when prompted.

---
author: Jan Grzegorowski
