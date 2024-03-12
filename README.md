# devops

# Create volumes for stateful services.
docker volume create redmine_postgresql
docker volume create redmine_redmine

# redmine install on docker

 docker run -d --name redmine --network redmine -v redmine_postgresql:/var/lib/postgresql -v redmine_redmine:/var/www/redmine -e "REDMINE_DB_HOST=redmine_postgresql" -e "REDMINE_DB_USERNAME=redmine" -e "REDMINE_DB_PASSWORD=password" -p 8080:3000 redmine:latest

Verify the container is running.
docker ps
