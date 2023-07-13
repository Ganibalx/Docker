sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ mkdir Контейнеризация
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ ды
ды: команда не найдена
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ ls
Diplom  Django  java  Python  SQL  Контейнеризация
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ shroot ./Контейнеризация /bin/bash
Команда «shroot» не найдена. Возможно, вы имели в виду:
  command 'schroot' from deb schroot (1.6.10-12ubuntu3.1)
  command 'chroot' from deb coreutils (8.32-4.1ubuntu1)
Try: sudo apt install <deb name>
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ chroot ./Контейнеризация /bin/bash
chroot: не удалось сменить корневой каталог на './Контейнеризация': Операция не позволена
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ sudo chroot ./Контейнеризация /bin/bash
[sudo] пароль для sergey: 
chroot: failed to run command ‘/bin/bash’: No such file or directory
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ mkdir Контейнеризация/bin
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ ldd /bin/bash
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ mkdir Контейнеризация
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ ды
ды: команда не найдена
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ ls
Diplom  Django  java  Python  SQL  Контейнеризация
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ shroot ./Контейнеризация /bin/bash
Команда «shroot» не найдена. Возможно, вы имели в виду:
  command 'schroot' from deb schroot (1.6.10-12ubuntu3.1)
  command 'chroot' from deb coreutils (8.32-4.1ubuntu1)
Try: sudo apt install <deb name>
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ chroot ./Контейнеризация /bin/bash
chroot: не удалось сменить корневой каталог на './Контейнеризация': Операция не позволена
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ sudo chroot ./Контейнеризация /bin/bash
[sudo] пароль для sergey: 
chroot: failed to run command ‘/bin/bash’: No such file or directory
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ mkdir Контейнеризация/bin
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ ldd /bin/bash
	linux-vdso.so.1 (0x00007ffdc1bfd000)
	libtinfo.so.6 => /lib/x86_64-linux-gnu/libtinfo.so.6 (0x00007f3e81561000)
	libc.so.6 => /lib/x86_64-linux-gnu/libc.so.6 (0x00007f3e81200000)
	/lib64/ld-linux-x86-64.so.2 (0x00007f3e81719000)
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ mkdir Контейнеризация/lib
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ mkdir Контейнеризация/lib64
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cp /bin/bush ./Контейнеризация/bin/
cp: не удалось выполнить stat для '/bin/bush': Нет такого файла или каталога
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cp /lib/x86_64-linux-gnu/libtinfo.so.6 ./Контейнеризация/lib/x86_64-linux-gnu/
cp: невозможно создать обычный файл './Контейнеризация/lib/x86_64-linux-gnu/': Это не каталог
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cp /lib/x86_64-linux-gnu/libtinfo.so.6 ./Контейнеризация/lib/
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cp /lib/x86_64-linux-gnu/libc.so.6 ./Контейнеризация/lib/
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cp /lib64/ld-linux-x86-64.so.2 ./Контейнеризация/lib64/
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ sudo chroot ./Контейнеризация /bin/bash
bash-5.1# exit     
exit
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ whereis ls
ls: /usr/bin/ls /usr/share/man/man1/ls.1.gz
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ mkdir ./Контейнеризация/usr
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cp /usr/bin/ls ./Контейнеризация/usr
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ ldd ls
ldd: ./ls: Нет такого файла или каталога
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ ldd /usr/bin/ls
	linux-vdso.so.1 (0x00007ffc199ed000)
	libselinux.so.1 => /lib/x86_64-linux-gnu/libselinux.so.1 (0x00007fb4d14a9000)
	libc.so.6 => /lib/x86_64-linux-gnu/libc.so.6 (0x00007fb4d1200000)
	libpcre2-8.so.0 => /lib/x86_64-linux-gnu/libpcre2-8.so.0 (0x00007fb4d1169000)
	/lib64/ld-linux-x86-64.so.2 (0x00007fb4d1519000)
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cp /lib/x86_64-linux-gnu/libselinux.so.1 ./Контейнеризация/lib
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cp /lib/x86_64-linux-gnu/libc.so.6 ./Контейнеризация/lib
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cp /lib/x86_64-linux-gnu/libpcre2-8.so.0 ./Контейнеризация/lib
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cp /lib64/ld-linux-x86-64.so.2 ./Контейнеризация/lib64
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ sudo chroot ./Контейнеризация /bin/bash
bash-5.1# ls
bash: ls: command not found
bash-5.1# ls -l
bash: ls: command not found
bash-5.1# exit
exit
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cd Контейнеризация/usr
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Контейнеризация/usr$ ls
ls
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Контейнеризация/usr$ mkdir bin
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Контейнеризация/usr$ cp ls ./bin
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Контейнеризация/usr$ rm ls
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Контейнеризация/usr$ ls
bin
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Контейнеризация/usr$ cd ..
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Контейнеризация$ cd ..
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ sudo chroot ./Контейнеризация /bin/bash
bash-5.1# ls
bin  lib  lib64  usr
bash-5.1# exit
exit
	linux-vdso.so.1 (0x00007ffdc1bfd000)
	libtinfo.so.6 => /lib/x86_64-linux-gnu/libtinfo.so.6 (0x00007f3e81561000)
	libc.so.6 => /lib/x86_64-linux-gnu/libc.so.6 (0x00007f3e81200000)
	/lib64/ld-linux-x86-64.so.2 (0x00007f3e81719000)
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ mkdir Контейнеризация/lib
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ mkdir Контейнеризация/lib64
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cp /bin/bush ./Контейнеризация/bin/
cp: не удалось выполнить stat для '/bin/bush': Нет такого файла или каталога
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cp /lib/x86_64-linux-gnu/libtinfo.so.6 ./Контейнеризация/lib/x86_64-linux-gnu/
cp: невозможно создать обычный файл './Контейнеризация/lib/x86_64-linux-gnu/': Это не каталог
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cp /lib/x86_64-linux-gnu/libtinfo.so.6 ./Контейнеризация/lib/
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cp /lib/x86_64-linux-gnu/libc.so.6 ./Контейнеризация/lib/
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cp /lib64/ld-linux-x86-64.so.2 ./Контейнеризация/lib64/
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ sudo chroot ./Контейнеризация /bin/bash
bash-5.1# exit     
exit
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ whereis ls
ls: /usr/bin/ls /usr/share/man/man1/ls.1.gz
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ mkdir ./Контейнеризация/usr
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cp /usr/bin/ls ./Контейнеризация/usr
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ ldd ls
ldd: ./ls: Нет такого файла или каталога
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ ldd /usr/bin/ls
	linux-vdso.so.1 (0x00007ffc199ed000)
	libselinux.so.1 => /lib/x86_64-linux-gnu/libselinux.so.1 (0x00007fb4d14a9000)
	libc.so.6 => /lib/x86_64-linux-gnu/libc.so.6 (0x00007fb4d1200000)
	libpcre2-8.so.0 => /lib/x86_64-linux-gnu/libpcre2-8.so.0 (0x00007fb4d1169000)
	/lib64/ld-linux-x86-64.so.2 (0x00007fb4d1519000)
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cp /lib/x86_64-linux-gnu/libselinux.so.1 ./Контейнеризация/lib
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cp /lib/x86_64-linux-gnu/libc.so.6 ./Контейнеризация/lib
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cp /lib/x86_64-linux-gnu/libpcre2-8.so.0 ./Контейнеризация/lib
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cp /lib64/ld-linux-x86-64.so.2 ./Контейнеризация/lib64
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ sudo chroot ./Контейнеризация /bin/bash
bash-5.1# ls
bash: ls: command not found
bash-5.1# ls -l
bash: ls: command not found
bash-5.1# exit
exit
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ cd Контейнеризация/usr
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Контейнеризация/usr$ ls
ls
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Контейнеризация/usr$ mkdir bin
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Контейнеризация/usr$ cp ls ./bin
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Контейнеризация/usr$ rm ls
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Контейнеризация/usr$ ls
bin
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Контейнеризация/usr$ cd ..
sergey@sergey-GA-78LMT-USB3-R2:~/Teach/Контейнеризация$ cd ..
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ sudo chroot ./Контейнеризация /bin/bash
bash-5.1# ls
bin  lib  lib64  usr
bash-5.1# exit
exit

