# Docker Compose for Matomo
Docker Compose (docker-compose.yml) for Matomo based on official Docker Image (https://hub.docker.com/_/matomo/) with Nginx (and Certbot included) and Redis ready


### Requirements
1. Git (e.g. https://desktop.github.com/)
2. Docker (https://docs.docker.com/install/)
3. Docker Compose (https://docs.docker.com/compose/)


### Usage
1. Clone this repo and go to repo folder
    ```bash
    git clone https://github.com/thalidzhokov/matomo-docker-compose.git && cd matomo-docker-compose
    ```
    
2. Copy `.env.dist` to `.env`
    ```bash
    cp .env.dist .env
    ```
    
3. Configure your project and set new strong password to database in `.env`
    ```bash
    nano .env
    ```
    
4. Run project 
    ```bash
    docker-compose up -d
    ```
    
5. Open it in browser (e.g. http://domaim.com) and install Matomo with your database configuration from `.env` 


### How to configure Redis?
Based on https://matomo.org/faq/how-to/faq_20511/

After installation add changes to `matomo/config/config.ini.php`
```bash
nano matomo/config/config.ini.php
```

```php
[Cache]
backend = chained

[ChainedCache]
backends[] = array
backends[] = redis

[RedisCache]
host = "redis" 
port = 6379
timeout = 0.0
password = ""
database = 14
; In case you are using queued tracking: Make sure to configure a different database! Otherwise queued requests will be flushed
```

