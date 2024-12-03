# SRS Nginx Docker

This project uses Docker to run [SRS](https://github.com/ossrs/srs) and [Nginx](https://github.com/nginx/nginx), enabling the HTTPS connection of SRS.

To use an HTTP connection, an SSL certificate is required. The [process of generation](https://ossrs.net/lts/en-us/docs/v5/doc/http-server) for SRS using OpenSSL is as follows:

```bash
# Key
openssl genrsa -out server.key 204

# Cert
openssl req -new -x509 -key server.key -out server.crt -days 3650 -subj "/C=CN/ST=Beijing/L=Beijing/O=Me/OU=Me/CN=ossrs.net"
```

Then move ```server.key``` and ```server.crt``` to ```./conf/certs```.

Use docker compose to run.

```bash
docker compose up
```