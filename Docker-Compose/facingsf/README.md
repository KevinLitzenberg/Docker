http://www.facingsf.com

An online street art photo blog. 

Uses three docker containers 
(1) nginx 1.17.8 (Alpine 8.3.0)
(1) mysql 8.0 (Ubuntu 16.04.01)
(1) php-fpm7.4 (Ubuntu 18.04) from phpdockerio  


docker-compose.yml file uses an .env file to populate the db users and password.  The .env file has not been added to the repo for obvious reasons.

webserver: Update /phpdocker/nginx/public/index.php and DisplayPhotoGallery01.html.php mysqli_connect password parameter from "change_me" to match whatever is being used in the .env file.

mysql: Has line commented to populate the database with a mysqldump file. This only needs to be run the first time to populate the php7-4-mysql-data volume.  Once persistant storage is populated there is no need to continue pushing the mysqldump

php-fpm image is from https://hub.docker.com/u/phpdockerio
