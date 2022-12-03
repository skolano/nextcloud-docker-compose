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
If your nextcloud is 