

### Word press

docker run -d --name server-wp -e WORDPRESS_DB_HOST=mysql_server2 -e WORDPRESS_DB_USER=nes -e WORDPRESS_DB_PASSWORD=1234 -e WORDPRESS_DB_NAME=grupo1 --network=net-wp --publish published=9300,target=80 wordpress
