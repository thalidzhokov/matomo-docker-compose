# Docker for Matomo
Docker Compose (docker-compose.yml) for Matomo based on official Docker Image (https://hub.docker.com/_/matomo/) with Nginx (and Certbot included) and Redis ready

### Requirements
1. Git (e.g. https://desktop.github.com/)
2. Docker (https://docs.docker.com/install/)
3. Docker Compose (https://docs.docker.com/compose/)

### Usage
1. Clone this repo and go to repo folder
    ```bash
    git clone https://github.com/thalidzhokov/matomo-docker.git && cd matomo-docker
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
