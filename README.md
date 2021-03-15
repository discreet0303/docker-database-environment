# Database Environment with Docker
Using docker to build a database environment

## Quick Start
* Clone the repository
```
git clone https://github.com/discreet0303/docker-database-environment.git
```
* Choose the database environment you want, then ```cd``` to folder
* Set each database config
* Run this command `docker-compose up -d`

## Environments
### (intel version)mysql:5.7.24 + phpmyadmin:latest

* `MYSQL_ROOT_PASSWORD` set mysql root password
    * check `mysql` and `phpmyadmin`  container have the same value
* You can set `phpmyadmin` config in `myadmin` folder, there are some initial value
    * `file_uploads`: on
    * `memory_limit`: 1000M
    * `upload_max_filesize`: 1000M
    * `post_max_size`: 1000M
    * `max_execution_time`: 600


### (arm64V8 version)amd64/mysql:8.0.23 + arm64v8/phpmyadmin:latest

* `MYSQL_ROOT_PASSWORD` set mysql root password
    * check `mysql` and `phpmyadmin`  container have the same value
* You can set `phpmyadmin` config in `myadmin` folder, there are some initial value
    * `file_uploads`: on
    * `memory_limit`: 1000M
    * `upload_max_filesize`: 1000M
    * `post_max_size`: 1000M
    * `max_execution_time`: 600


#### upload the large sql file by command line
1. Put the exported sql file in the mysql shared folder.
2. Login to mysql container
```
docker exec -it MYSQL_CONTAINER_ID bash
```
3. Login to MySQL
```
mysql -u USERNAME -p
```
4. create a database
```
create database DB_NAME;
```
5. use the database you just created
```
use DB_NAME;
```
6. import the sql file
```
source /path/to/file.sql
```

