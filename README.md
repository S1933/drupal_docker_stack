DRUPAL DOCKER DEVELOPMENT ENVIRONMENT
===================================

This repository contains a Docker-based development environment for Drupal.

Requirements
-----------
- Docker
- Docker Compose
- Git

Quick Start
-----------
1. Clone this repository
2. Copy .env.example to .env and adjust values as needed
3. Run: `docker-compose up -d`
4. Access the site at: http://localhost

Container Structure
-----------------
- Web (Drupal/PHP)
- PostgreSQL
- Traefik (Reverse Proxy)

Database Connection
```
Host: postgres
Port: 5432
Database: drupal
Username: drupal
Password: [see .env file]
```


Common Commands
-------------
# Start containers
`docker-compose up -d`

# Stop containers
`docker-compose down`

# View logs
`docker-compose logs -f`

# Access Drupal container
`docker exec -it drupal-web-1 sh`

# Run Drush commands
`docker exec -it drupal-web-1 drush [command]`

Development Notes
---------------
- Settings.php is located in web/sites/default/
- Custom modules should be placed in web/modules/custom/
- Custom themes should be placed in web/themes/custom/

Troubleshooting
--------------
1. If database connection fails:
   - Verify PostgreSQL container is running
   - Check database credentials in settings.php
   - Ensure service names match in docker-compose.yml

2. If Traefik issues occur:
   - Check Traefik dashboard at localhost:8080
   - Verify labels in docker-compose.yml
   - Check entrypoints configuration

Maintenance
----------
- Regularly update Drupal core and modules
- Back up database before major changes
- Monitor container logs for issues

Security Notes
-------------
- Never commit `.env` file
- Keep hash_salt in settings.php private
- Regularly update all containers
- Follow Drupal security advisories

Support
-------
For issues and support:
1. Check container logs
2. Review Drupal documentation
3. Consult Docker documentation
4. Open an issue in the repository
