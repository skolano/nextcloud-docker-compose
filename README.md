# Nextcloud - Docker Compose

## Requirements
- docker
- docker compose

## Installation

###  Download repo
```bash
git clone "https://github.com/skolano/nextcloud-docker-compose"
```

### Choose  scenario
`docker-compose.yml` - This is default installation file. Docker compose will run containers with **mariadb**, **nextcloud**,  **redis** and **PHPMyAdmin**
`docker-compose-proxy.yml` - This file contains all components from default installation and **Nginx Proxy Manager**.

### Run docker compose
#### Default scenario 
```bash
cd nextcloud-docker-compose
```

```bash
docker compose up -d
```

#### Proxy scenario
```bash
cd nextcloud-docker-compose
```

Rename rename file
```bash
mv docker-compose-proxy.yml docker-compose.yml
```

Run docker compose
```bash
docker compose up -d
```

##### Proxy configuration

Go to your Nginx Proxy Manager `https://yoururl:81`
```bash
login: admin@example.com
Password: changeme
```



## SSL Self-Signed
If your nextcloud is # Nextcloud - Docker Compose

## Requirements
- docker
- docker compose

## Installation

###  Download repo
```bash
git clone "https://github.com/skolano/nextcloud-docker-compose"
```

### Choose  scenario
`docker-compose.yml` - This is default installation file. Docker compose will run containers with **mariadb**, **nextcloud**,  **redis** and **PHPMyAdmin**
`docker-compose-proxy.yml` - This file contains all components from default installation and **Nginx Proxy Manager**.

### Run docker compose
#### Default scenario 
```bash
cd nextcloud-docker-compose
```

```bash
docker compose up -d
```

#### Proxy scenario
```bash
cd nextcloud-docker-compose
```

Rename rename file
```bash
mv docker-compose-proxy.yml docker-compose.yml
```

Run docker compose
```bash
docker compose up -d
```

### Proxy configuration

Go to your Nginx Proxy Manager `https://yoururl:81`
```bash
login: admin@example.com
Password: changeme
```



## SSL Self-Signed
If your nextcloud is in your local network and you want to use ssl follow this steps:

Make direcotry for certificate and key
```bash
mkdir /var/lib/docker/volumes/nextcloud_apache2/_data/ssl
```

Move apache configuration file
```bash
cp nextcloud.conf /var/lib/docker/volumes/nextcloud_apache2/_data/sites-enabled/
```

Change directory
```bash
cd /var/lib/docker/volumes/nextcloud_apache2/_data/ssl
```

Generate self-signed certificate and key
```bash
sudo openssl req -x509 -nodes -days 364 -newkey rsa:2048 -keyout key.key -out cert.pem
```

Enable apache2 configuration
```bash
docker exec nextcloud a2enmod ssl
```

Restart docker container
```bash
docker restart nextcloud
```
