sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ sudo ip netns exec testns123 bash
root@sergey-GA-78LMT-USB3-R2:/home/sergey/Teach# ip a
1: lo: <LOOPBACK> mtu 65536 qdisc noop state DOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
root@sergey-GA-78LMT-USB3-R2:/home/sergey/Teach# ip a
1: lo: <LOOPBACK> mtu 65536 qdisc noop state DOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
3: veth1@if4: <BROADCAST,MULTICAST> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 92:d2:67:ab:f7:24 brd ff:ff:ff:ff:ff:ff link-netnsid 0
root@sergey-GA-78LMT-USB3-R2:/home/sergey/Teach# sudo ip addr add 10.0.0.2/24 dev veth1
root@sergey-GA-78LMT-USB3-R2:/home/sergey/Teach# sudo ip link set dev veth1 up
root@sergey-GA-78LMT-USB3-R2:/home/sergey/Teach# ping 10.0.0.1
PING 10.0.0.1 (10.0.0.1) 56(84) bytes of data.
64 bytes from 10.0.0.1: icmp_seq=1 ttl=64 time=0.085 ms
64 bytes from 10.0.0.1: icmp_seq=2 ttl=64 time=0.049 ms
64 bytes from 10.0.0.1: icmp_seq=3 ttl=64 time=0.049 ms
64 bytes from 10.0.0.1: icmp_seq=4 ttl=64 time=0.056 ms
64 bytes from 10.0.0.1: icmp_seq=5 ttl=64 time=0.056 ms
64 bytes from 10.0.0.1: icmp_seq=6 ttl=64 time=0.057 ms
64 bytes from 10.0.0.1: icmp_seq=7 ttl=64 time=0.057 ms
64 bytes from 10.0.0.1: icmp_seq=8 ttl=64 time=0.044 ms
64 bytes from 10.0.0.1: icmp_seq=9 ttl=64 time=0.058 ms
64 bytes from 10.0.0.1: icmp_seq=10 ttl=64 time=0.056 ms
64 bytes from 10.0.0.1: icmp_seq=11 ttl=64 time=0.056 ms
^C
--- 10.0.0.1 ping statistics ---
11 packets transmitted, 11 received, 0% packet loss, time 10232ms
rtt min/avg/max/mdev = 0.044/0.056/0.085/0.009 ms


sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ sudo ip link add veth0 type veth peer name veth1
[sudo] пароль для sergey: 
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: enp3s0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether b4:2e:99:29:ea:76 brd ff:ff:ff:ff:ff:ff
    inet 192.168.0.8/24 brd 192.168.0.255 scope global dynamic noprefixroute enp3s0
       valid_lft 7590sec preferred_lft 7590sec
    inet6 fe80::7ac2:8c15:cb72:6374/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
3: veth1@veth0: <BROADCAST,MULTICAST,M-DOWN> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 92:d2:67:ab:f7:24 brd ff:ff:ff:ff:ff:ff
4: veth0@veth1: <BROADCAST,MULTICAST,M-DOWN> mtu 1500 qdisc noop state DOWN group default qlen 1000
    link/ether 5e:7a:80:86:de:dd brd ff:ff:ff:ff:ff:ff
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ sudo ip link set veth1 netns testns123
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ sudo ip addr add 10.0.0.1/24 dev veth0
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ sudo ip link set dev veth0 up
sergey@sergey-GA-78LMT-USB3-R2:~/Teach$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host 
       valid_lft forever preferred_lft forever
2: enp3s0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether b4:2e:99:29:ea:76 brd ff:ff:ff:ff:ff:ff
    inet 192.168.0.8/24 brd 192.168.0.255 scope global dynamic noprefixroute enp3s0
       valid_lft 7277sec preferred_lft 7277sec
    inet6 fe80::7ac2:8c15:cb72:6374/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
4: veth0@if3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default qlen 1000
    link/ether 5e:7a:80:86:de:dd brd ff:ff:ff:ff:ff:ff link-netns testns123
    inet 10.0.0.1/24 scope global veth0
       valid_lft forever preferred_lft forever
    inet6 fe80::5c7a:80ff:fe86:dedd/64 scope link 
       valid_lft forever preferred_lft forever
