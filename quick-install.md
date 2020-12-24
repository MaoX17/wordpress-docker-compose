# Quick Install ... la versione rapida

```
mkdir -p /opt/docker

git clone https://github.com/MaoX17/wordpress-docker-compose.git

cd wordpress-docker-compose

docker network create proxy

cd 00_traefik

Genero la stringa di auth:

htpasswd -n username

ottengo:

username:$apr1$VDSty0Wy$5nrZ7nthjusltZXM0eE2s/

Copio la stringa e la inserisco nel file [traefik_dynamic.toml](00_traefik/conf/traefik_dynamic.toml)

Sempre nello stesso file sostituisi

rule = "Host(`traefik.proietti.net`)"

con il tuo indirizzo per il manager di traefik

Nel file [traefik.toml](00_traefik/conf/traefik.toml)
sostituire 
email = "maurizio.proietti(AT)EMAIL.com"
Con la vostra email

Poi

docker-compose build
docker-compose up -d


```

E Traefik è installato e funzionante

Passiamo a WP

```

cp wp05/env.example wp05/.env

Modifica il file .env con i dati che vuoi

cd wp05

mkdir data/redis

cp conf/redis.conf wp05/redis/

Modifica il Dockerfile

poi

docker-compose build
docker-compose up -d


```
