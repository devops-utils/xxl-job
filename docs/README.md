```shell
git pull
mvn package
mvn clean package

mysql -h127.0.0.1 -uroot -p

create database xxl_job default character set utf8mb4 collate utf8mb4_unicode_ci;
use xxl_job;
create user 'nessaj'@'127.0.0.1' identified by 'nessaj';
grant all privileges on xxl_job.* to 'nessaj'@'127.0.0.1';
create user 'nessaj'@'%' identified by 'nessaj';
grant all privileges on xxl_job.* to 'nessaj'@'%';
flush privileges;

nessaj
```

```shell
172.17.0.2
172.21.16.11
```