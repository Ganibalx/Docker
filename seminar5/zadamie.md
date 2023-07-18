sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB/Docker/seminar5$ nano Dockerfile
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB/Docker/seminar5$ nano docker-comsergeysergeysersergey@sessssesssergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB/Docker/seminar5$ docker copmose up
docker: 'copmose' is not a docker command.
See 'docker --help'
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB/Docker/seminar5$ docker compose up
validating /home/sergey/Teach/Docker/GB/Docker/seminar5/docker-compose.yml: services.adminer.deploy Additional property node is not allowed
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB/Docker/seminar5$ nano Dockerfile
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB/Docker/seminar5$ nano docker-compose.yml
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Docker/GB/Docker/seminar5$ docker compose up
[+] Running 8/8
 ✔ adminer 7 layers [⣿⣿⣿⣿⣿⣿⣿]      0B/0B      Pulled                                                      22.8s 
   ✔ 34df401c391c Pull complete                                                                           11.3s 
   ✔ 942860e9b081 Pull complete                                                                           16.3s 
   ✔ f571177b537e Pull complete                                                                           16.7s 
   ✔ 78d7a59571f8 Pull complete                                                                           17.1s 
   ✔ 530e7e02f755 Pull complete                                                                           17.4s 
   ✔ 03ee8734c62c Pull complete                                                                           17.9s 
   ✔ ed7a0cc37cf2 Pull complete                                                                           18.7s 
[+] Building 14.1s (6/6) FINISHED                                                                               
 => [db internal] load .dockerignore                                                                       0.9s
 => => transferring context: 2B                                                                            0.1s
 => [db internal] load build definition from Dockerfile                                                    1.1s
 => => transferring dockerfile: 75B                                                                        0.0s
 => [db internal] load metadata for docker.io/library/mariadb:10.10.2                                      0.0s
 => CACHED [db 1/2] FROM docker.io/library/mariadb:10.10.2                                                 0.0s
 => [db 2/2] RUN mkdir /test                                                                              10.7s
 => [db] exporting to image                                                                                1.0s
 => => exporting layers                                                                                    0.9s
 => => writing image sha256:0f6092c3b58621ea11c7cb4871ae273e1f2fee932ed715b84419435468b61255               0.1s
 => => naming to docker.io/library/seminar5-db                                                             0.1s
[+] Running 4/4
 ✔ Network seminar5_default      Created                                                                   0.5s 
 ✔ Container seminar5-db-2       Created                                                                   2.9s 
 ✔ Container seminar5-adminer-1  Created                                                                   2.0s 
 ✔ Container seminar5-db-1       Created                                                                   2.9s 
Attaching to seminar5-adminer-1, seminar5-db-1, seminar5-db-2
seminar5-adminer-1  | [Tue Jul 18 19:59:11 2023] PHP 7.4.33 Development Server (http://[::]:8080) started
seminar5-db-1       | 2023-07-18 19:59:12+00:00 [Note] [Entrypoint]: Entrypoint script for MariaDB Server 1:10.10.2+maria~ubu2204 started.
seminar5-db-2       | 2023-07-18 19:59:13+00:00 [Note] [Entrypoint]: Entrypoint script for MariaDB Server 1:10.10.2+maria~ubu2204 started.
seminar5-db-1       | 2023-07-18 19:59:15+00:00 [Note] [Entrypoint]: Switching to dedicated user 'mysql'
seminar5-db-2       | 2023-07-18 19:59:15+00:00 [Note] [Entrypoint]: Switching to dedicated user 'mysql'
seminar5-db-2       | 2023-07-18 19:59:15+00:00 [Note] [Entrypoint]: Entrypoint script for MariaDB Server 1:10.10.2+maria~ubu2204 started.
seminar5-db-1       | 2023-07-18 19:59:15+00:00 [Note] [Entrypoint]: Entrypoint script for MariaDB Server 1:10.10.2+maria~ubu2204 started.
seminar5-db-2       | 2023-07-18 19:59:16+00:00 [Note] [Entrypoint]: Initializing database files
seminar5-db-1       | 2023-07-18 19:59:16+00:00 [Note] [Entrypoint]: Initializing database files
seminar5-db-1       | 
seminar5-db-1       | 
seminar5-db-1       | PLEASE REMEMBER TO SET A PASSWORD FOR THE MariaDB root USER !
seminar5-db-1       | To do so, start the server, then issue the following command:
seminar5-db-1       | 
seminar5-db-1       | '/usr/bin/mysql_secure_installation'
seminar5-db-1       | 
seminar5-db-1       | which will also give you the option of removing the test
seminar5-db-1       | databases and anonymous user created by default.  This is
seminar5-db-1       | strongly recommended for production servers.
seminar5-db-1       | 
seminar5-db-1       | See the MariaDB Knowledgebase at https://mariadb.com/kb
seminar5-db-1       | 
seminar5-db-1       | Please report any problems at https://mariadb.org/jira
seminar5-db-1       | 
seminar5-db-1       | The latest information about MariaDB is available at https://mariadb.org/.
seminar5-db-1       | 
seminar5-db-1       | Consider joining MariaDB's strong and vibrant community:
seminar5-db-1       | https://mariadb.org/get-involved/
seminar5-db-1       | 
seminar5-db-1       | 
seminar5-db-1       | 2023-07-18 20:00:15+00:00 [Note] [Entrypoint]: Database files initialized
seminar5-db-1       | 2023-07-18 20:00:15+00:00 [Note] [Entrypoint]: Starting temporary server
seminar5-db-1       | 2023-07-18 20:00:15+00:00 [Note] [Entrypoint]: Waiting for server startup
seminar5-db-1       | 2023-07-18 20:00:15 0 [Note] mariadbd (server 10.10.2-MariaDB-1:10.10.2+maria~ubu2204) starting as process 103 ...
seminar5-db-1       | 2023-07-18 20:00:15 0 [Note] InnoDB: Compressed tables use zlib 1.2.11
seminar5-db-1       | 2023-07-18 20:00:15 0 [Note] InnoDB: Number of transaction pools: 1
seminar5-db-1       | 2023-07-18 20:00:15 0 [Note] InnoDB: Using crc32 + pclmulqdq instructions
seminar5-db-1       | 2023-07-18 20:00:15 0 [Note] mariadbd: O_TMPFILE is not supported on /tmp (disabling future attempts)
seminar5-db-1       | 2023-07-18 20:00:15 0 [Note] InnoDB: Using liburing
seminar5-db-1       | 2023-07-18 20:00:15 0 [Note] InnoDB: Initializing buffer pool, total size = 128.000MiB, chunk size = 2.000MiB
seminar5-db-1       | 2023-07-18 20:00:15 0 [Note] InnoDB: Completed initialization of buffer pool
seminar5-db-1       | 2023-07-18 20:00:15 0 [Note] InnoDB: File system buffers for log disabled (block size=4096 bytes)
seminar5-db-2       | 
seminar5-db-2       | 
seminar5-db-2       | PLEASE REMEMBER TO SET A PASSWORD FOR THE MariaDB root USER !
seminar5-db-2       | To do so, start the server, then issue the following command:
seminar5-db-2       | 
seminar5-db-2       | '/usr/bin/mysql_secure_installation'
seminar5-db-2       | 
seminar5-db-2       | which will also give you the option of removing the test
seminar5-db-2       | databases and anonymous user created by default.  This is
seminar5-db-2       | strongly recommended for production servers.
seminar5-db-2       | 
seminar5-db-2       | See the MariaDB Knowledgebase at https://mariadb.com/kb
seminar5-db-2       | 
seminar5-db-2       | Please report any problems at https://mariadb.org/jira
seminar5-db-2       | 
seminar5-db-2       | The latest information about MariaDB is available at https://mariadb.org/.
seminar5-db-2       | 
seminar5-db-2       | Consider joining MariaDB's strong and vibrant community:
seminar5-db-2       | https://mariadb.org/get-involved/
seminar5-db-2       | 
seminar5-db-2       | 
seminar5-db-2       | 2023-07-18 20:00:15+00:00 [Note] [Entrypoint]: Database files initialized
seminar5-db-2       | 2023-07-18 20:00:15+00:00 [Note] [Entrypoint]: Starting temporary server
seminar5-db-2       | 2023-07-18 20:00:15+00:00 [Note] [Entrypoint]: Waiting for server startup
seminar5-db-2       | 2023-07-18 20:00:15 0 [Note] mariadbd (server 10.10.2-MariaDB-1:10.10.2+maria~ubu2204) starting as process 102 ...
seminar5-db-2       | 2023-07-18 20:00:16 0 [Note] InnoDB: Compressed tables use zlib 1.2.11
seminar5-db-2       | 2023-07-18 20:00:16 0 [Note] InnoDB: Number of transaction pools: 1
seminar5-db-2       | 2023-07-18 20:00:16 0 [Note] InnoDB: Using crc32 + pclmulqdq instructions
seminar5-db-2       | 2023-07-18 20:00:16 0 [Note] mariadbd: O_TMPFILE is not supported on /tmp (disabling future attempts)
seminar5-db-2       | 2023-07-18 20:00:16 0 [Note] InnoDB: Using liburing
seminar5-db-2       | 2023-07-18 20:00:16 0 [Note] InnoDB: Initializing buffer pool, total size = 128.000MiB, chunk size = 2.000MiB
seminar5-db-2       | 2023-07-18 20:00:16 0 [Note] InnoDB: Completed initialization of buffer pool
seminar5-db-2       | 2023-07-18 20:00:16 0 [Note] InnoDB: File system buffers for log disabled (block size=4096 bytes)
seminar5-db-1       | 2023-07-18 20:00:16 0 [Note] InnoDB: 128 rollback segments are active.
seminar5-db-1       | 2023-07-18 20:00:16 0 [Note] InnoDB: Setting file './ibtmp1' size to 12.000MiB. Physically writing the file full; Please wait ...
seminar5-db-1       | 2023-07-18 20:00:16 0 [Note] InnoDB: File './ibtmp1' size is now 12.000MiB.
seminar5-db-1       | 2023-07-18 20:00:16 0 [Note] InnoDB: log sequence number 46456; transaction id 14
seminar5-db-1       | 2023-07-18 20:00:16 0 [Note] Plugin 'FEEDBACK' is disabled.
seminar5-db-1       | 2023-07-18 20:00:16 0 [Warning] 'user' entry 'root@70f744ba7741' ignored in --skip-name-resolve mode.
seminar5-db-1       | 2023-07-18 20:00:16 0 [Warning] 'proxies_priv' entry '@% root@70f744ba7741' ignored in --skip-name-resolve mode.
seminar5-db-2       | 2023-07-18 20:00:16 0 [Note] InnoDB: 128 rollback segments are active.
seminar5-db-2       | 2023-07-18 20:00:16 0 [Note] InnoDB: Setting file './ibtmp1' size to 12.000MiB. Physically writing the file full; Please wait ...
seminar5-db-2       | 2023-07-18 20:00:16 0 [Note] InnoDB: File './ibtmp1' size is now 12.000MiB.
seminar5-db-2       | 2023-07-18 20:00:16 0 [Note] InnoDB: log sequence number 46456; transaction id 14
seminar5-db-2       | 2023-07-18 20:00:16 0 [Note] Plugin 'FEEDBACK' is disabled.
seminar5-db-2       | 2023-07-18 20:00:16 0 [Warning] 'user' entry 'root@77f28c96c4fb' ignored in --skip-name-resolve mode.
seminar5-db-2       | 2023-07-18 20:00:16 0 [Warning] 'proxies_priv' entry '@% root@77f28c96c4fb' ignored in --skip-name-resolve mode.
seminar5-db-1       | 2023-07-18 20:00:16 0 [Note] mariadbd: ready for connections.
seminar5-db-1       | Version: '10.10.2-MariaDB-1:10.10.2+maria~ubu2204'  socket: '/run/mysqld/mysqld.sock'  port: 0  mariadb.org binary distribution
seminar5-db-2       | 2023-07-18 20:00:16 0 [Note] mariadbd: ready for connections.
seminar5-db-2       | Version: '10.10.2-MariaDB-1:10.10.2+maria~ubu2204'  socket: '/run/mysqld/mysqld.sock'  port: 0  mariadb.org binary distribution
seminar5-db-1       | 2023-07-18 20:00:17+00:00 [Note] [Entrypoint]: Temporary server started.
seminar5-db-2       | 2023-07-18 20:00:17+00:00 [Note] [Entrypoint]: Temporary server started.
seminar5-db-2       | 2023-07-18 20:00:26+00:00 [Note] [Entrypoint]: Securing system users (equivalent to running mysql_secure_installation)
seminar5-db-1       | 2023-07-18 20:00:26+00:00 [Note] [Entrypoint]: Securing system users (equivalent to running mysql_secure_installation)
seminar5-db-2       | 
seminar5-db-2       | 
seminar5-db-2       | 2023-07-18 20:00:26+00:00 [Note] [Entrypoint]: Stopping temporary server
seminar5-db-2       | 2023-07-18 20:00:26 0 [Note] mariadbd (initiated by: unknown): Normal shutdown
seminar5-db-2       | 2023-07-18 20:00:26 0 [Note] InnoDB: FTS optimize thread exiting.
seminar5-db-1       | 
seminar5-db-1       | 
seminar5-db-1       | 2023-07-18 20:00:26+00:00 [Note] [Entrypoint]: Stopping temporary server
seminar5-db-1       | 2023-07-18 20:00:26 0 [Note] mariadbd (initiated by: unknown): Normal shutdown
seminar5-db-1       | 2023-07-18 20:00:26 0 [Note] InnoDB: FTS optimize thread exiting.
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] InnoDB: Starting shutdown...
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] InnoDB: Dumping buffer pool(s) to /var/lib/mysql/ib_buffer_pool
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] InnoDB: Buffer pool(s) dump completed at 230718 20:00:27
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] InnoDB: Starting shutdown...
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] InnoDB: Dumping buffer pool(s) to /var/lib/mysql/ib_buffer_pool
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] InnoDB: Buffer pool(s) dump completed at 230718 20:00:27
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] InnoDB: Removed temporary tablespace data file: "./ibtmp1"
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] InnoDB: Shutdown completed; log sequence number 46456; transaction id 15
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] InnoDB: Removed temporary tablespace data file: "./ibtmp1"
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] InnoDB: Shutdown completed; log sequence number 46456; transaction id 15
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] mariadbd: Shutdown complete
seminar5-db-2       | 
seminar5-db-2       | 
seminar5-db-2       | 2023-07-18 20:00:27+00:00 [Note] [Entrypoint]: Temporary server stopped
seminar5-db-2       | 
seminar5-db-2       | 
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] mariadbd: Shutdown complete
seminar5-db-1       | 
seminar5-db-1       | 
seminar5-db-2       | 2023-07-18 20:00:27+00:00 [Note] [Entrypoint]: MariaDB init process done. Ready for start up.
seminar5-db-2       | 
seminar5-db-2       | 
seminar5-db-1       | 2023-07-18 20:00:27+00:00 [Note] [Entrypoint]: Temporary server stopped
seminar5-db-1       | 
seminar5-db-1       | 
seminar5-db-1       | 2023-07-18 20:00:27+00:00 [Note] [Entrypoint]: MariaDB init process done. Ready for start up.
seminar5-db-1       | 
seminar5-db-1       | 
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] mariadbd (server 10.10.2-MariaDB-1:10.10.2+maria~ubu2204) starting as process 1 ...
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] mariadbd (server 10.10.2-MariaDB-1:10.10.2+maria~ubu2204) starting as process 1 ...
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] InnoDB: Compressed tables use zlib 1.2.11
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] InnoDB: Number of transaction pools: 1
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] InnoDB: Using crc32 + pclmulqdq instructions
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] mariadbd: O_TMPFILE is not supported on /tmp (disabling future attempts)
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] InnoDB: Using liburing
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] InnoDB: Initializing buffer pool, total size = 128.000MiB, chunk size = 2.000MiB
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] InnoDB: Completed initialization of buffer pool
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] InnoDB: Compressed tables use zlib 1.2.11
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] InnoDB: Number of transaction pools: 1
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] InnoDB: Using crc32 + pclmulqdq instructions
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] mariadbd: O_TMPFILE is not supported on /tmp (disabling future attempts)
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] InnoDB: Using liburing
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] InnoDB: Initializing buffer pool, total size = 128.000MiB, chunk size = 2.000MiB
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] InnoDB: Completed initialization of buffer pool
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] InnoDB: File system buffers for log disabled (block size=4096 bytes)
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] InnoDB: File system buffers for log disabled (block size=4096 bytes)
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] InnoDB: 128 rollback segments are active.
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] InnoDB: Setting file './ibtmp1' size to 12.000MiB. Physically writing the file full; Please wait ...
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] InnoDB: File './ibtmp1' size is now 12.000MiB.
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] InnoDB: 128 rollback segments are active.
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] InnoDB: log sequence number 46456; transaction id 14
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] Plugin 'FEEDBACK' is disabled.
seminar5-db-2       | 2023-07-18 20:00:27 0 [Note] InnoDB: Loading buffer pool(s) from /var/lib/mysql/ib_buffer_pool
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] InnoDB: Setting file './ibtmp1' size to 12.000MiB. Physically writing the file full; Please wait ...
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] InnoDB: File './ibtmp1' size is now 12.000MiB.
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] InnoDB: log sequence number 46456; transaction id 14
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] InnoDB: Loading buffer pool(s) from /var/lib/mysql/ib_buffer_pool
seminar5-db-1       | 2023-07-18 20:00:27 0 [Note] Plugin 'FEEDBACK' is disabled.
seminar5-db-2       | 2023-07-18 20:00:28 0 [Warning] You need to use --log-bin to make --expire-logs-days or --binlog-expire-logs-seconds work.
seminar5-db-1       | 2023-07-18 20:00:28 0 [Warning] You need to use --log-bin to make --expire-logs-days or --binlog-expire-logs-seconds work.
seminar5-db-1       | 2023-07-18 20:00:28 0 [Note] InnoDB: Buffer pool(s) load completed at 230718 20:00:28
seminar5-db-2       | 2023-07-18 20:00:28 0 [Note] Server socket created on IP: '0.0.0.0'.
seminar5-db-1       | 2023-07-18 20:00:28 0 [Note] Server socket created on IP: '0.0.0.0'.
seminar5-db-2       | 2023-07-18 20:00:28 0 [Note] Server socket created on IP: '::'.
seminar5-db-1       | 2023-07-18 20:00:28 0 [Note] Server socket created on IP: '::'.
seminar5-db-2       | 2023-07-18 20:00:28 0 [Note] InnoDB: Buffer pool(s) load completed at 230718 20:00:28
seminar5-db-2       | 2023-07-18 20:00:28 0 [Note] mariadbd: ready for connections.
seminar5-db-2       | Version: '10.10.2-MariaDB-1:10.10.2+maria~ubu2204'  socket: '/run/mysqld/mysqld.sock'  port: 3306  mariadb.org binary distribution
seminar5-db-1       | 2023-07-18 20:00:28 0 [Note] mariadbd: ready for connections.
seminar5-db-1       | Version: '10.10.2-MariaDB-1:10.10.2+maria~ubu2204'  socket: '/run/mysqld/mysqld.sock'  port: 3306  mariadb.org binary distribution
seminar5-adminer-1  | [Tue Jul 18 20:02:46 2023] [::ffff:172.18.0.1]:39954 Accepted
seminar5-adminer-1  | [Tue Jul 18 20:02:47 2023] [::ffff:172.18.0.1]:39954 [200]: GET /
seminar5-adminer-1  | [Tue Jul 18 20:02:47 2023] [::ffff:172.18.0.1]:39954 Closing
seminar5-adminer-1  | [Tue Jul 18 20:02:47 2023] [::ffff:172.18.0.1]:39958 Accepted
seminar5-adminer-1  | [Tue Jul 18 20:02:47 2023] [::ffff:172.18.0.1]:39958 [200]: GET /?file=default.css&version=4.8.1
seminar5-adminer-1  | [Tue Jul 18 20:02:47 2023] [::ffff:172.18.0.1]:39958 Closing
seminar5-adminer-1  | [Tue Jul 18 20:02:47 2023] [::ffff:172.18.0.1]:39962 Accepted
seminar5-adminer-1  | [Tue Jul 18 20:02:47 2023] [::ffff:172.18.0.1]:39962 [200]: GET /?file=functions.js&version=4.8.1
seminar5-adminer-1  | [Tue Jul 18 20:02:47 2023] [::ffff:172.18.0.1]:39962 Closing
seminar5-adminer-1  | [Tue Jul 18 20:02:47 2023] [::ffff:172.18.0.1]:39974 Accepted
seminar5-adminer-1  | [Tue Jul 18 20:02:47 2023] [::ffff:172.18.0.1]:39974 [200]: GET /?file=favicon.ico&version=4.8.1
seminar5-adminer-1  | [Tue Jul 18 20:02:47 2023] [::ffff:172.18.0.1]:39974 Closing
seminar5-adminer-1  | [Tue Jul 18 20:02:48 2023] [::ffff:172.18.0.1]:39980 Accepted
seminar5-adminer-1  | [Tue Jul 18 20:02:48 2023] [::ffff:172.18.0.1]:39980 [200]: POST /?script=version
seminar5-adminer-1  | [Tue Jul 18 20:02:48 2023] [::ffff:172.18.0.1]:39980 Closing
seminar5-adminer-1  | [Tue Jul 18 20:02:57 2023] [::ffff:172.18.0.1]:36226 Accepted
seminar5-adminer-1  | [Tue Jul 18 20:02:57 2023] [::ffff:172.18.0.1]:36226 [302]: POST /
seminar5-adminer-1  | [Tue Jul 18 20:02:57 2023] [::ffff:172.18.0.1]:36226 Closing
seminar5-adminer-1  | [Tue Jul 18 20:02:57 2023] [::ffff:172.18.0.1]:36238 Accepted
seminar5-db-1       | 2023-07-18 20:02:57 3 [Warning] Access denied for user 'admin'@'172.18.0.3' (using password: YES)
seminar5-adminer-1  | [Tue Jul 18 20:02:57 2023] [::ffff:172.18.0.1]:36238 [403]: GET /?server=db&username=admin
seminar5-adminer-1  | [Tue Jul 18 20:02:57 2023] [::ffff:172.18.0.1]:36238 Closing
seminar5-adminer-1  | [Tue Jul 18 20:02:57 2023] [::ffff:172.18.0.1]:36250 Accepted
seminar5-adminer-1  | [Tue Jul 18 20:03:03 2023] [::ffff:172.18.0.1]:36250 Closed without sending a request; it was probably just an unused speculative preconnection
seminar5-adminer-1  | [Tue Jul 18 20:03:03 2023] [::ffff:172.18.0.1]:36250 Closing
seminar5-adminer-1  | [Tue Jul 18 20:03:48 2023] [::ffff:172.18.0.1]:36834 Accepted
seminar5-adminer-1  | [Tue Jul 18 20:03:48 2023] [::ffff:172.18.0.1]:36834 [200]: GET /
seminar5-adminer-1  | [Tue Jul 18 20:03:48 2023] [::ffff:172.18.0.1]:36834 Closing
seminar5-adminer-1  | [Tue Jul 18 20:03:48 2023] [::ffff:172.18.0.1]:36846 Accepted
seminar5-adminer-1  | [Tue Jul 18 20:03:48 2023] [::ffff:172.18.0.1]:36846 [200]: GET /?file=default.css&version=4.8.1
seminar5-adminer-1  | [Tue Jul 18 20:03:48 2023] [::ffff:172.18.0.1]:36846 Closing
seminar5-adminer-1  | [Tue Jul 18 20:03:48 2023] [::ffff:172.18.0.1]:36860 Accepted
seminar5-adminer-1  | [Tue Jul 18 20:03:48 2023] [::ffff:172.18.0.1]:36860 [200]: GET /?file=functions.js&version=4.8.1
seminar5-adminer-1  | [Tue Jul 18 20:03:48 2023] [::ffff:172.18.0.1]:36860 Closing
seminar5-adminer-1  | [Tue Jul 18 20:03:59 2023] [::ffff:172.18.0.1]:43078 Accepted
seminar5-adminer-1  | [Tue Jul 18 20:03:59 2023] [::ffff:172.18.0.1]:43078 [302]: POST /?server=db&username=admin
seminar5-adminer-1  | [Tue Jul 18 20:03:59 2023] [::ffff:172.18.0.1]:43078 Closing
seminar5-adminer-1  | [Tue Jul 18 20:03:59 2023] [::ffff:172.18.0.1]:43086 Accepted
seminar5-adminer-1  | [Tue Jul 18 20:03:59 2023] [::ffff:172.18.0.1]:43086 [200]: GET /?server=db&username=root
seminar5-adminer-1  | [Tue Jul 18 20:03:59 2023] [::ffff:172.18.0.1]:43086 Closing
seminar5-adminer-1  | [Tue Jul 18 20:03:59 2023] [::ffff:172.18.0.1]:43090 Accepted
seminar5-adminer-1  | [Tue Jul 18 20:03:59 2023] [::ffff:172.18.0.1]:43090 [200]: GET /?file=jush.js&version=4.8.1
seminar5-adminer-1  | [Tue Jul 18 20:03:59 2023] [::ffff:172.18.0.1]:43090 Closing
seminar5-adminer-1  | [Tue Jul 18 20:03:59 2023] [::ffff:172.18.0.1]:43094 Accepted
seminar5-adminer-1  | [Tue Jul 18 20:04:05 2023] [::ffff:172.18.0.1]:43094 Closed without sending a request; it was probably just an unused speculative preconnection
seminar5-adminer-1  | [Tue Jul 18 20:04:05 2023] [::ffff:172.18.0.1]:43094 Closing
seminar5-adminer-1  | [Tue Jul 18 20:04:05 2023] [::ffff:172.18.0.1]:43108 Accepted
seminar5-adminer-1  | [Tue Jul 18 20:04:10 2023] [::ffff:172.18.0.1]:43108 Closed without sending a request; it was probably just an unused speculative preconnection
seminar5-adminer-1  | [Tue Jul 18 20:04:10 2023] [::ffff:172.18.0.1]:43108 Closing
seminar5-adminer-1  | [Tue Jul 18 20:04:23 2023] [::ffff:172.18.0.1]:56744 Accepted
seminar5-adminer-1  | [Tue Jul 18 20:04:28 2023] [::ffff:172.18.0.1]:56744 Closed without sending a request; it was probably just an unused speculative preconnection
seminar5-adminer-1  | [Tue Jul 18 20:04:28 2023] [::ffff:172.18.0.1]:56744 Closing
seminar5-db-2       | 2023-07-18 20:05:35 0 [Note] mariadbd (initiated by: unknown): Normal shutdown
seminar5-db-2       | 2023-07-18 20:05:35 0 [Note] InnoDB: FTS optimize thread exiting.
seminar5-db-2       | 2023-07-18 20:05:35 0 [Note] InnoDB: Starting shutdown...
seminar5-db-2       | 2023-07-18 20:05:35 0 [Note] InnoDB: Dumping buffer pool(s) to /var/lib/mysql/ib_buffer_pool
seminar5-db-2       | 2023-07-18 20:05:35 0 [Note] InnoDB: Buffer pool(s) dump completed at 230718 20:05:35
seminar5-db-1       | 2023-07-18 20:05:35 0 [Note] mariadbd (initiated by: unknown): Normal shutdown
seminar5-db-1       | 2023-07-18 20:05:35 0 [Note] InnoDB: FTS optimize thread exiting.
seminar5-db-1       | 2023-07-18 20:05:35 0 [Note] InnoDB: Starting shutdown...
seminar5-db-1       | 2023-07-18 20:05:35 0 [Note] InnoDB: Dumping buffer pool(s) to /var/lib/mysql/ib_buffer_pool
seminar5-db-1       | 2023-07-18 20:05:35 0 [Note] InnoDB: Buffer pool(s) dump completed at 230718 20:05:35
seminar5-db-2       | 2023-07-18 20:05:36 0 [Note] InnoDB: Removed temporary tablespace data file: "./ibtmp1"
seminar5-db-2       | 2023-07-18 20:05:36 0 [Note] InnoDB: Shutdown completed; log sequence number 46640; transaction id 15
seminar5-db-1       | 2023-07-18 20:05:36 0 [Note] InnoDB: Removed temporary tablespace data file: "./ibtmp1"
seminar5-db-1       | 2023-07-18 20:05:36 0 [Note] InnoDB: Shutdown completed; log sequence number 46640; transaction id 15
seminar5-db-2       | 2023-07-18 20:05:36 0 [Note] mariadbd: Shutdown complete
seminar5-db-2       | 
seminar5-db-2       | 
seminar5-db-1       | 2023-07-18 20:05:36 0 [Note] mariadbd: Shutdown complete
seminar5-db-1       | 
seminar5-db-1       | 
seminar5-adminer-1 exited with code 0
seminar5-adminer-1 exited with code 0
seminar5-db-2 exited with code 0
seminar5-db-2 exited with code 0
seminar5-db-1 exited with code 0
