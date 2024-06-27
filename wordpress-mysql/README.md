- Deploy with docker compose
docker compose up -d

- chack running containers
docker ps


Navigate to http://localhost:80 in your web browser to access WordPress.


Stop and remove the containers

docker compose down

To remove all WordPress data, delete the named volumes by passing the -v parameter:

docker compose down -v

Source: https://github.com/docker/awesome-compose/blob/master/wordpress-mysql/README.md