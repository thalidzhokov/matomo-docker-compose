# Docker for Matomo
Docker Compose (docker-compose.yml) for Matomo based on official Docker Image (https://github.com/matomo-org/docker) with Nginx (and Certbot included) and Redis ready

### Requirements
1. Git (e.g. https://desktop.github.com/)
2. Docker (https://docs.docker.com/install/)
3. Docker Compose (https://docs.docker.com/compose/)

### Usage
1. Copy `.env.dist` to `.env`
    ```bash
    cp .env.dist .env
    ```
    
2. Configure your project and set new strong password to database in `.env`
    ```bash
    nano .env
    ```
    
3. Run project 
    ```bash
    docker-compose up -d
    ```
