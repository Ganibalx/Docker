sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB/Docker$ nano seminar4/Dockerfile
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB/Docker$ docker build -t mymariadb ./seminar4/
[+] Building 2.0s (7/7) FINISHED                                                                                             docker:default
 => [internal] load build definition from Dockerfile                                                                                   0.3s
 => => transferring dockerfile: 111B                                                                                                   0.0s
 => [internal] load .dockerignore                                                                                                      0.3s
 => => transferring context: 2B                                                                                                        0.0s
 => [internal] load metadata for docker.io/library/mariadb:10.10.2                                                                     0.0s
 => [internal] load build context                                                                                                      0.3s
 => => transferring context: 33B                                                                                                       0.0s
 => [1/2] FROM docker.io/library/mariadb:10.10.2                                                                                       0.0s
 => CACHED [2/2] COPY mariadb.cnf /etc/mysql/conf.d                                                                                    0.0s
 => exporting to image                                                                                                                 0.2s
 => => exporting layers                                                                                                                0.0s
 => => writing image sha256:d1f284e430f6fc06081ee565c8f9534eaab2ba1c47ad3c6e095bacaf3f16115e                                           0.1s
 => => naming to docker.io/library/mymariadb                                                                                           0.1s
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB/Docker$ docker run --name mymariadb -e MARIADB_ROOT_PASSWORD=test123 -v ./mariadb:/var/lib/mysql -d mymariadb
aede4097864cb35e6b5e277a98a57e367b16694731180ab6111fcee85a303234
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB/Docker$ docker ps
CONTAINER ID   IMAGE       COMMAND                  CREATED         STATUS         PORTS      NAMES
aede4097864c   mymariadb   "docker-entrypoint.s…"   9 seconds ago   Up 6 seconds   3306/tcp   mymariadb
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB/Docker$ docker exec -it aede4097864c bash
root@aede4097864c:/# mysql -u root -p
Warning: skipping '!includedir /etc/mysql/mariadb.conf.d/' directive as maximum includerecursion level was reached in file /etc/mysql/conf.d/mariadb.cnf at line 8
Warning: skipping '!includedir /etc/mysql/conf.d/' directive as maximum includerecursion level was reached in file /etc/mysql/conf.d/mariadb.cnf at line 9
Enter password: 
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 3
Server version: 10.10.2-MariaDB-1:10.10.2+maria~ubu2204 mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MariaDB [(none)]> CREATE DATABASE HW3;
Query OK, 1 row affected (0.001 sec)

MariaDB [(none)]> show databases;
+--------------------+
| Database           |
+--------------------+
| HW3                |
| information_schema |
| mysql              |
| performance_schema |
| sys                |
+--------------------+
5 rows in set (0.001 sec)

MariaDB [(none)]> exit
Bye
root@aede4097864c:/# exit
exit
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB/Docker$ docker ps
CONTAINER ID   IMAGE       COMMAND                  CREATED         STATUS         PORTS      NAMES
aede4097864c   mymariadb   "docker-entrypoint.s…"   2 minutes ago   Up 2 minutes   3306/tcp   mymariadb
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB/Docker$ docker run --name phpmyadmin -d --link mymariadb:db -p 8081:80 phpmyadmin/phpmyadmin
Unable to find image 'phpmyadmin/phpmyadmin:latest' locally
latest: Pulling from phpmyadmin/phpmyadmin
f1f26f570256: Pull complete 
ee0a4e40ccac: Pull complete 
5ca9fb408faa: Pull complete 
5baa808a48ff: Pull complete 
6e8d74e4d8ee: Pull complete 
fac8e70fcf67: Pull complete 
b3b7906fb177: Pull complete 
cb4935bbeb83: Pull complete 
c9e00ef337e3: Pull complete 
cfe495c8d695: Pull complete 
dcc3fd107f0c: Pull complete 
fe3c587d1f07: Pull complete 
677f27d94442: Pull complete 
4d778a8cb653: Pull complete 
5f0f7b557ecd: Pull complete 
6ad259d60f7c: Pull complete 
41acd705cbc4: Pull complete 
912204d5a7e6: Pull complete 
Digest: sha256:ed87921184b59f7d8fc85c6a5f041c22758a4d4419c0ee3bac38eb7e133eaed3
Status: Downloaded newer image for phpmyadmin/phpmyadmin:latest
a0f113daeb06e0ffdf2d5541eaaf6235ed48435223a26335545ac8637998565e
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB/Docker$ docker ps
CONTAINER ID   IMAGE                   COMMAND                  CREATED          STATUS          PORTS                                   NAMES
a0f113daeb06   phpmyadmin/phpmyadmin   "/docker-entrypoint.…"   24 seconds ago   Up 11 seconds   0.0.0.0:8081->80/tcp, :::8081->80/tcp   phpmyadmin
aede4097864c   mymariadb               "docker-entrypoint.s…"   6 minutes ago    Up 6 minutes    3306/tcp                                mymariadb
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB/Docker$ 
