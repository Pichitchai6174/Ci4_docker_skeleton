# Ci4_docker_skeleton

A basic infrastructure for developing applications with CodeIgniter 4 integrated with Docker in a simple and flexible way.  
This setup is designed for PHP developers who want to start projects quickly without wasting time managing environment configurations.

---

## Features

- Ready-to-use Docker environment with PHP 8.1 and Apache  
- Pre-installed necessary PHP extensions for CodeIgniter 4  
- MySQL 8 database container with persistent volume  
- phpMyAdmin container for easy database management  
- Composer installed and ready inside the container  
- Apache configuration with mod_rewrite enabled for clean URLs  
- Volume mounting for live code editing without rebuilding containers  
- Environment variable support for easy configuration

---

## Getting Started

### Prerequisites

- [Docker](https://www.docker.com/get-started) installed on your machine  
- [Docker Compose](https://docs.docker.com/compose/install/) installed  

### Installation

1. Clone this repository

   ```bash
   git clone https://github.com/pichitchai6174/Ci4_docker_skeleton.git
   cd Ci4_docker_skeleton

2. Copy .env.example to .env and update your environment variables (database credentials, app URL, etc.)
3. Build and start the Docker containers

   ```bash
   docker-compose up -d --build

4. Access your application at http://localhost:8080 (or your configured port)
5. Access phpMyAdmin at http://localhost:8081 for database management (or your configured port)

## Configuration
- PHP configuration file is mounted from ./docker/php/php.ini — you can customize PHP settings there
- MySQL configuration file is mounted from ./docker/mysql/my.cnf
- Application environment variables are managed in .env

## Folder Structure

   ```bash
  Ci4_docker_skeleton/
  ├── app/                 # Your CodeIgniter 4 application code
  ├── docker/
  │   ├── apache/          # Apache configuration files
  │   ├── mysql/           # MySQL configuration files
  │   └── php/             # PHP configuration files
  ├── writable/            # Writable folder for logs, cache, sessions
  ├── docker-compose.yml   # Docker Compose configuration
  ├── Dockerfile           # Dockerfile for PHP/Apache container
  ├── composer.json        # Composer dependencies
  └── .env.example         # Example environment variables
  ```

## Troubleshooting
- If you encounter permission issues, make sure the writable/ folder has correct permissions
- To rebuild containers without cache:
  ```bash
  docker-compose build --no-cache
  docker-compose up -d
  ```
- If Composer fails due to missing PHP extensions, verify that your Dockerfile installs all required extensions

## License
This project is licensed under the MIT License. See the LICENSE file for details.
