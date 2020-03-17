A single docker-compose container to run mysql.

(1) mysql 8.0 (Ubuntu 16.04.01)

docker-compose.yml file uses an .env file to populate the db users and password.  The .env file has not been added to the repo for obvious reasons.

example: .env

MYSQL_ROOT_PSWD=password
MYSQL_USER=mysql_user
MYSQL_USER_PSWD=user_password
MYSQL_DATABASE=userdb
