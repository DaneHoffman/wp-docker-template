# Production-ready Wordpress Docker-compose Template

Services included in this docker-compose.yml file: 

* `wordpress`: Contains the Wordpress CMS and relevant PHP files
* `mariadb`: Database required for Wordpress container to operate, stores all site content
* `phpmyadmin`: Allows database management through a web interface
* `wpcli`: Command-line wordpress administration, use if WP interface is not available or for automated tasks
* `healthcheck`: A wpcli instance that automatically checks containers to see if they started correctly


Requirements:

* `docker` and `docker-compose`
* Basic knowledge of how docker works


## What does it do? 
This repository is designed to create a new Wordpress stack using docker containers. It can be deployed either on a live web server or on your local machine and used as a consistent, containerized hosting environment. 

When using a reverse proxy like Traefik or Nginx, it can be used to host multiple Wordpress sites on the same server. 

## How do I use it? 
1. Clone this repository and rename it 
2. Fill out the variables in the `.env` (environment variables) file. _Note: Make sure to add this to .gitignore! This should be kept separate between environments and never uploaded to Github_ 
3. Start up the stack by running `docker-compose up -d`
4. Log into the Wordpress web interface via `http://localhost:8000`




## Best Practices
* Use specific container version tags in the .env file. Do not use `latest` for production environments, since the `latest` version is rolling and it will be impossible to maintain consistency between different environments
* Encode all passwords in the `.env` file
