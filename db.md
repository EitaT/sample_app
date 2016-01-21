# OracleDB on Docker

## DockerRegistry
* docker-registry.rjbdev.jp
* ec2 InstanceID：i-f6e6ef05

## Container
```console
docker run -d -p 49160:22 -p 1521:1521 -p 18000:18000 docker-registry.rjbdev.jp/rjb-architect/fan-db
```
* 49160:22 SSH
* 1521:1521 OracleDB
* 18000:18000 DockerRemoteAPI

#### SSH
```console
$ docker exec -d CONTAINER_ID /usr/sbin/sshd -D
$ ssh -o StrictHostKeyChecking=no -o UserKnownHostsFile=/dev/null root@localhost -p 49160
$ su oracle
  password:admin
$ sqlplus system/oracle as sysdba
```

## OracleDB
#### URL
jdbc:oracle:thin:@HOSTNAME:1521:XE
 
#### UserName
SA52

#### Password
fnavi_2983_noah
