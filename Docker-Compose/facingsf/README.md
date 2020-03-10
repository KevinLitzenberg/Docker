http://www.facingsf.com

An online street art photo blog. 

Uses three docker containers 
(1) nginx 1.17.8 (Alpine 8.3.0)
(1) mysql 8.0 (Ubuntu 16.04.01)
(1) php-fpm7.4 (Ubuntu 18.04) from phpdockerio  


docker-compose.yml file uses an .env file to populate the db users and password.  The .env file has not been added to the repo for obvious reasons.

example: .env

MYSQL_ROOT_PSWD=password
MYSQL_USER=mysql_user
MYSQL_USER_PSWD=user_password
MYSQL_DATABASE=userdb

webserver: The php mysqli_connect password is pulled from an external file in the ./phpdocker/nginx/php_sql_config.ini. 

php_sql_config.ini: example

[database]
servername = name_of_docker-compose_service
username = name_of_mysql_docker-compose_user
password = password_of_docker-compose_user
dbname = name_of_mysql_docker-compose_database

/phpdocker/nginx/public/index.php and Di$splayPhotoGallery01.html.php both need the file

mysql: Has line populate the database with a mysqldump file. This only needs to be run the first time to populate the php7-4-mysql-data volume.  Once persistant storage is populated there is no need to continue pushing the mysqldump

If you change passwords you willl need to recreate the volume or update the mysqldb.

php-fpm image is from https://hub.docker.com/u/phpdockerio
