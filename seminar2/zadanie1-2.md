sergey@sergey-GA-78LMT-USB3-R2:~$ sudo lxc-create -n name -t ubuntu
[sudo] пароль для sergey: 
Checking cache download in /var/cache/lxc/jammy/rootfs-amd64 ... 
Installing packages in template: apt-transport-https,ssh,vim,language-pack-en,language-pack-ru
Downloading ubuntu jammy minimal ...
I: Target architecture can be executed
I: Retrieving InRelease 
I: Checking Release signature
I: Valid Release signature (key id F6ECB3762474EDA9D21B7022871920D1991BC93C)
I: Retrieving Packages 
I: Validating Packages 
I: Retrieving Packages 

...

Current default time zone: 'Etc/UTC'
Local time is now:      Thu Jul 13 20:59:01 UTC 2023.
Universal Time is now:  Thu Jul 13 20:59:01 UTC 2023.


##
# The default user is 'ubuntu' with password 'ubuntu'!
# Use the 'sudo' command to run tasks as root in the container.
##

sergey@sergey-GA-78LMT-USB3-R2:~$ sudo lxc-start -n
[sudo] пароль для sergey: 
lxc-start: option requires an argument -- 'n'
Usage: lxc-start --name=NAME -- COMMAND

lxc-start start COMMAND in specified container NAME

Options :
  -n, --name=NAME        NAME of the container
  -d, --daemon           Daemonize the container (default)
  -F, --foreground       Start with the current tty attached to /dev/console
  -p, --pidfile=FILE     Create a file with the process id
  -f, --rcfile=FILE      Load configuration file FILE
  -c, --console=FILE     Use specified FILE for the container console
  -L, --console-log=FILE Log container console output to FILE
  -C, --close-all-fds    If any fds are inherited, close them
                         Note: --daemon implies --close-all-fds
  -s, --define KEY=VAL   Assign VAL to configuration variable KEY
      --share-[net|ipc|uts|pid]=NAME Share a namespace with another container or pid

Common options :
  -o, --logfile=FILE               Output log to FILE instead of stderr
  -l, --logpriority=LEVEL          Set log priority to LEVEL
  -q, --quiet                      Don't produce any output
  -P, --lxcpath=PATH               Use specified container path
  -?, --help                       Give this help list
      --usage                      Give a short usage message
      --version                    Print the version number

Mandatory or optional arguments to long options are also mandatory or optional
for any corresponding short options.

See the lxc-start man page for further information.

sergey@sergey-GA-78LMT-USB3-R2:~$ sudo lxc-start -n name
sergey@sergey-GA-78LMT-USB3-R2:~$ sudo lxc-ls
name 
sergey@sergey-GA-78LMT-USB3-R2:~$ free -m
               total        used        free      shared  buff/cache   available
Память:      15970        4394        5726        1140        5849       10120
Подкачка:       2047           0        2047
sergey@sergey-GA-78LMT-USB3-R2:~$ sudo lxc-attach -n name
root@name:/# exit
exit
sergey@sergey-GA-78LMT-USB3-R2:~$ sudo lxs-cgroup -n name memory.max 256M
sudo: lxs-cgroup: команда не найдена
sergey@sergey-GA-78LMT-USB3-R2:~$ sudo lxc-cgroup -n name memory.max 256M
sergey@sergey-GA-78LMT-USB3-R2:~$ sudo lxc-attach -n name
root@name:/# free -m
               total        used        free      shared  buff/cache   available
Память:        256          27         224           0           4         228
Подкачка:          0           0           0
root@name:/# 
