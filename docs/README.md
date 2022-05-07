```shell
git pull
mvn package
mvn clean package

cd xxl-job-admin
sudo docker build -f Dockerfile -t yiluxiangbei/xxl-job-admin:v1.0 .
sudo docker push yiluxiangbei/xxl-job-admin:v1.0

cd ..
sudo docker run -ti -d --name=xxl-job-admin -p 8089:8080 --volume="$(pwd)":/xxl-job yiluxiangbei/xxl-job-admin:v1.0

sudo docker logs -f xxl-job-admin

mysql -h127.0.0.1 -uroot -p

create database xxl_job default character set utf8mb4 collate utf8mb4_unicode_ci;
use xxl_job;
create user 'nessaj'@'127.0.0.1' identified by 'nessaj';
grant all privileges on xxl_job.* to 'nessaj'@'127.0.0.1';
create user 'nessaj'@'%' identified by 'nessaj';
grant all privileges on xxl_job.* to 'nessaj'@'%';
flush privileges;

mysql -h127.0.0.1 -uroot -p xxl_job < doc/db/tables_xxl_job.sql

http://49.232.6.131:8089/xxl-job-admin
admin
123456

nessaj
```

```shell
172.17.0.2
172.21.16.11
```