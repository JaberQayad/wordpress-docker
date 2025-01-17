# WordPress Docker Compose Setup

This repository contains a Docker Compose configuration for setting up a WordPress site with a MariaDB database.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

- Docker
- Docker Compose

### Installation

1. Clone the repository:

    ```sh
    git clone https://github.com/JaberQayad/wordpress-docker.git
    cd your-repo-name
    ```

2. Create a `.env` file based on the `.env.example`:

    ```sh
    cp .env.example .env
    ```

3. Edit the `.env` file and update the environment variables with your own values:

    ```env
    WORDPRESS_DB_HOST=db
    WORDPRESS_DB_USER=yourusername
    WORDPRESS_DB_PASSWORD=yourpassword
    WORDPRESS_DB_NAME=wordpress
    PUID=1000
    PGID=100
    MYSQL_ROOT_PASSWORD=yourpassword
    TZ=Europe/Brussels
    MYSQL_DATABASE=wordpress
    MYSQL_USER=yourusername
    MYSQL_PASSWORD=yourpassword
    WORDPRESS_VOLUME_PATH=/path/to/wordpress/wordpress
    DB_VOLUME_PATH=/path/to/wordpress/Wordpressdb
    WORDPRESS_THEMES_PATH=/path/to/wordpress/themes
    WORDPRESS_PLUGINS_PATH=/path/to/wordpress/plugins
    WORDPRESS_UPLOADS_PATH=/path/to/wordpress/uploads
    ```

4. Create the required directories and set permissions:

    ```sh
    sudo mkdir -p /path/to/wordpress/wordpress
    sudo mkdir -p /path/to/wordpress/themes
    sudo mkdir -p /path/to/wordpress/plugins
    sudo mkdir -p /path/to/wordpress/uploads
    sudo mkdir -p /path/to/wordpress/Wordpressdb

    sudo chown -R www-data:www-data /path/to/wordpress/wordpress
    sudo chown -R www-data:www-data /path/to/wordpress/themes
    sudo chown -R www-data:www-data /path/to/wordpress/plugins
    sudo chown -R www-data:www-data /path/to/wordpress/uploads
    sudo chown -R www-data:www-data /path/to/wordpress/Wordpressdb

    sudo chmod -R 755 /path/to/wordpress/wordpress
    sudo chmod -R 755 /path/to/wordpress/themes
    sudo chmod -R 755 /path/to/wordpress/plugins
    sudo chmod -R 755 /path/to/wordpress/uploads
    sudo chmod -R 755 /path/to/wordpress/Wordpressdb
    ```

5. Start the services:

    ```sh
    docker-compose up -d
    ```

6. Access your WordPress site at `http://localhost:8383`. 


