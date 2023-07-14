sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ mkdir mariadb
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ docker run --name mariadb -e MARIADB_ROOT_PASSWORD=test123 -v ./mariadb:/var/lib/mysql -d mariadb:10.10.2
docker: permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Post "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/containers/create?name=mariadb": dial unix /var/run/docker.sock: connect: permission denied.
See 'docker run --help'.
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ sudo docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ sudo docker run --name mariadb -e MARIADB_ROOT_PASSWORD=test123 -v ./mariadb:/var/lib/mysql -d mariadb:10.10.2Unable to find image 'mariadb:10.10.2' locally
10.10.2: Pulling from library/mariadb
10ac4908093d: Pull complete 
44779101e748: Pull complete 
a721db3e3f3d: Pull complete 
1850a929b84a: Pull complete 
397a918c7da3: Pull complete 
806be17e856d: Pull complete 
634de6c90876: Pull complete 
cd00854cfb1a: Pull complete 
Digest: sha256:bfc25a68e113de43d0d112f5a7126df8e278579c3224e3923359e1c1d8d5ce6e
Status: Downloaded newer image for mariadb:10.10.2
a51ede5bb06e855830ba3660ccaea6d0b305bf3c56e09586710f2d4632bcd012
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ sudo docker ps
CONTAINER ID   IMAGE             COMMAND                  CREATED          STATUS         PORTS      NAMES
a51ede5bb06e   mariadb:10.10.2   "docker-entrypoint.s…"   16 seconds ago   Up 4 seconds   3306/tcp   mariadb
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ sudo usermod sergey -aG docker
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ docker ps
permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Get "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/containers/json": dial unix /var/run/docker.sock: connect: permission denied
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ sudo chmod 666 /var/run/docker.sock
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ docker ps
CONTAINER ID   IMAGE             COMMAND                  CREATED         STATUS         PORTS      NAMES
a51ede5bb06e   mariadb:10.10.2   "docker-entrypoint.s…"   7 minutes ago   Up 7 minutes   3306/tcp   mariadb
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ docker exec -it a51ede5bb06e bash
root@a51ede5bb06e:/# ls -l
total 56
lrwxrwxrwx   1 root root    7 Jan 26 02:03 bin -> usr/bin
drwxr-xr-x   2 root root 4096 Apr 18  2022 boot
drwxr-xr-x   5 root root  340 Jul 14 19:45 dev
drwxr-xr-x   2 root root 4096 Jan 31 18:42 docker-entrypoint-initdb.d
drwxr-xr-x   1 root root 4096 Jul 14 19:45 etc
drwxr-xr-x   2 root root 4096 Apr 18  2022 home
lrwxrwxrwx   1 root root    7 Jan 26 02:03 lib -> usr/lib
lrwxrwxrwx   1 root root    9 Jan 26 02:03 lib32 -> usr/lib32
lrwxrwxrwx   1 root root    9 Jan 26 02:03 lib64 -> usr/lib64
lrwxrwxrwx   1 root root   10 Jan 26 02:03 libx32 -> usr/libx32
drwxr-xr-x   2 root root 4096 Jan 26 02:03 media
drwxr-xr-x   2 root root 4096 Jan 26 02:03 mnt
drwxr-xr-x   2 root root 4096 Jan 26 02:03 opt
dr-xr-xr-x 382 root root    0 Jul 14 19:45 proc
drwx------   1 root root 4096 Jan 31 18:42 root
drwxr-xr-x   1 root root 4096 Jan 31 18:43 run
lrwxrwxrwx   1 root root    8 Jan 26 02:03 sbin -> usr/sbin
drwxr-xr-x   2 root root 4096 Jan 26 02:03 srv
dr-xr-xr-x  13 root root    0 Jul 14 19:45 sys
drwxrwxrwt   1 root root 4096 Jul 14 19:46 tmp
drwxr-xr-x   1 root root 4096 Jan 26 02:03 usr
drwxr-xr-x   1 root root 4096 Jan 26 02:06 var
root@a51ede5bb06e:/# mysql -u root -p
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
root@a51ede5bb06e:/# exit
exit
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ docker ps
CONTAINER ID   IMAGE             COMMAND                  CREATED          STATUS          PORTS      NAMES
a51ede5bb06e   mariadb:10.10.2   "docker-entrypoint.s…"   12 minutes ago   Up 12 minutes   3306/tcp   mariadb
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ docker stop mariadb
mariadb
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ docker run mariadb
Unable to find image 'mariadb:latest' locally
latest: Pulling from library/mariadb
9d19ee268e0d: Pull complete 
718e898a86ff: Pull complete 
43bd7a143a6c: Pull complete 
80cdf483b70a: Pull complete 
8c13b197eea7: Pull complete 
fe76c18bf258: Pull complete 
67fa5c829e7f: Pull complete 
a5cb79f31ff6: Pull complete 
Digest: sha256:f94bb4868d953fed5220c9d3cdc8449f4c314efb07d3a18eefa6010b383f2ab8
Status: Downloaded newer image for mariadb:latest
^C
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ docker ps -a
CONTAINER ID   IMAGE             COMMAND                  CREATED          STATUS                          PORTS     NAMES
60019289bea3   mariadb           "docker-entrypoint.s…"   37 seconds ago   Created                                   jovial_mclean
a51ede5bb06e   mariadb:10.10.2   "docker-entrypoint.s…"   14 minutes ago   Exited (0) About a minute ago             mariadb
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ docker run a51ede5bb06e
Unable to find image 'a51ede5bb06e:latest' locally
docker: Error response from daemon: pull access denied for a51ede5bb06e, repository does not exist or may require 'docker login': denied: requested access to the resource is denied.
See 'docker run --help'.
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ docker ps -a
CONTAINER ID   IMAGE             COMMAND                  CREATED              STATUS                          PORTS     NAMES
60019289bea3   mariadb           "docker-entrypoint.s…"   About a minute ago   Created                                   jovial_mclean
a51ede5bb06e   mariadb:10.10.2   "docker-entrypoint.s…"   15 minutes ago       Exited (0) About a minute ago             mariadb
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ sudo docker run --name mariadb -e MARIADB_ROOT_PASSWORD=test123 -v ./mariadb:/var/lib/mysql -d mariadb:10.10.2
docker: Error response from daemon: Conflict. The container name "/mariadb" is already in use by container "a51ede5bb06e855830ba3660ccaea6d0b305bf3c56e09586710f2d4632bcd012". You have to remove (or rename) that container to be able to reuse that name.
See 'docker run --help'.
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ docker stert a51ede5bb06e
docker: 'stert' is not a docker command.
See 'docker --help'
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ docker start a51ede5bb06e
a51ede5bb06e
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ docker ps
CONTAINER ID   IMAGE             COMMAND                  CREATED          STATUS          PORTS      NAMES
a51ede5bb06e   mariadb:10.10.2   "docker-entrypoint.s…"   18 minutes ago   Up 20 seconds   3306/tcp   mariadb
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ docker exec -it a51ede5bb06e bash
root@a51ede5bb06e:/# mysql -u root -p
Enter password: 
Welcome to the MariaDB monitor.  Commands end with ; or \g.
Your MariaDB connection id is 3
Server version: 10.10.2-MariaDB-1:10.10.2+maria~ubu2204 mariadb.org binary distribution

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

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
root@a51ede5bb06e:/# exit
exit
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ ls
Docker  mariadb
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ cd mariadb
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB/mariadb$ ls
aria_log.00000001  ddl_recovery.log  ib_buffer_pool  ib_logfile0  multi-master.info  mysql_upgrade_info  sys
aria_log_control   HW3               ibdata1         ibtmp1       mysql              performance_schema
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB/mariadb$ cd ..
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ sudo docker run --name phpmyadmin -d --link mariadb:db -p 8081:80 phpmyadmin/phpmyadmin
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
fb36fde242bce850d6f8ed573fed3c41441973965f35c4a8721a2e57384c6045
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ docker ps
CONTAINER ID   IMAGE                   COMMAND                  CREATED          STATUS          PORTS                                   NAMES
fb36fde242bc   phpmyadmin/phpmyadmin   "/docker-entrypoint.…"   41 seconds ago   Up 34 seconds   0.0.0.0:8081->80/tcp, :::8081->80/tcp   phpmyadmin
a51ede5bb06e   mariadb:10.10.2         "docker-entrypoint.s…"   26 minutes ago   Up 8 minutes    3306/tcp                                mariadb
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB$ 
