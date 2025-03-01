# Lab 1: Containerization

## 1. Docker command to create and run a container named `dbserver-mysql-nairobi`

Use the `customized-ubuntu:1.0` image to create a container named `dbserver-mysql-nairobi`. The command should map the container’s port 3306 to the host’s port 3309.

```dockerfile
docker run --name dbserver-mysql-nairobi -d -p 3306:3309 customized-ubuntu:1.0
```

## 2. MySQL Server and MySQL Client Installation in Ubuntu

```shell
docker pull mysql:latest
docker run --name mysql-server -e MYSQL_ROOT_PASSWORD=5trathmore -p 3309:3306 -d mysql:latest
```

## 3. Login using the MySQL Client and Change the MySQL Root Password

```sql
ALTER USER 'root'@'localhost' IDENTIFIED BY '5trathmore';
FLUSH PRIVILEGES;
docker exec -it mysql-server mysql -uroot -p
```
