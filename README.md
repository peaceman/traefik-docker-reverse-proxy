# traefik docker reverse proxy via docker-compose
## install & configuration
create a filled .env file from .env.example

create the specified external docker network

`docker network create $GATEWAY_NETWORK_NAME`

### acme
a sample configuration to use letsencrypt certificates resides in the `docker-compose.override.yml.example` file and can be used by removing the `.example` suffix. 

this sample config will use the tls alpn challenge and stores its credentials in the folder `./acme`

## further services
services that should be reachable via this traefik reverse proxy need to join the configured external docker network. a sample docker-compose service file, that uses acme to receive its certificates, and the predefined force-tls middleware is supplied in the sample-service folder