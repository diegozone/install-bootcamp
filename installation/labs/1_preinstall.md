# 1.Swappiness Settings

Below the commands , I have done,to set the swappiness correctly on the all nodes
```
[root@node05 ~]# sysctl -w vm.swappiness=1
vm.swappiness = 1
[root@node05 ~]# more /etc/sysctl.conf
vm.swappiness=1
[root@node05 ~]# cat /proc/sys/vm/swappiness
1
```
# 2.Show the mount attributes of your volume(s)

Below, the disks configuration
```
[root@node05 ~]# df -Th

Filesystem     Type      Size  Used Avail Use% Mounted on
/dev/sda2      xfs        30G  1.2G   29G   5% /
devtmpfs       devtmpfs  7.9G     0  7.9G   0% /dev
tmpfs          tmpfs     7.9G     0  7.9G   0% /dev/shm
tmpfs          tmpfs     7.9G  9.3M  7.9G   1% /run
tmpfs          tmpfs     7.9G     0  7.9G   0% /sys/fs/cgroup
/dev/sdc       xfs      1023G   33M 1023G   1% /data
/dev/sda1      xfs       497M   81M  417M  17% /boot
/dev/sdb1      ext4       32G   49M   30G   1% /mnt/resource
tmpfs          tmpfs     1.6G     0  1.6G   0% /run/user/1000
tmpfs          tmpfs     1.6G     0  1.6G   0% /run/user/0
```

the fstab file
```
[root@node05 ~]# more /etc/fstab

#
# /etc/fstab
# Created by anaconda on Wed Aug 15 19:30:54 2018
#
# Accessible filesystems, by reference, are maintained under '/dev/disk'
# See man pages fstab(5), findfs(8), mount(8) and/or blkid(8) for more info
#
UUID=12907c8a-6b2f-4981-b94c-f3cd772270a7 /                       xfs     defaults        0 0
UUID=fa2f8157-21c9-43b6-85e3-ff04422dfa00 /boot                   xfs     defaults        0 0
/dev/sdc                                  /data                   xfs     defaults        0 0
```

# 3.If you have ext-based volume
  I have mounted only an xfs volume

# 4.Transparent_hugepage settings

Below the command I have executed on the all nodes
```
[root@node05 ~]# echo never > /sys/kernel/mm/transparent_hugepage/enabled
[root@node05 ~]# echo never > /sys/kernel/mm/transparent_hugepage/defrag
[root@node05 ~]# more /etc/rc.local
touch /var/lock/subsys/local
if test -f /sys/kernel/mm/transparent_hugepage/enabled; then 
    echo never > /sys/kernel/mm/transparent_hugepage/enabled   
    echo never > /sys/kernel/mm/transparent_hugepage/defrag  
fi
```
# 5.List your network interface configuration

below , the result of ifconfig command

```
[root@node05 ~]# ifconfig -a
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 10.0.1.12  netmask 255.255.255.0  broadcast 10.0.1.255
        inet6 fe80::20d:3aff:fe44:4976  prefixlen 64  scopeid 0x20<link>
        ether 00:0d:3a:44:49:76  txqueuelen 1000  (Ethernet)
        RX packets 26703  bytes 7283110 (6.9 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 30621  bytes 6037139 (5.7 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

eth1: flags=6211<UP,BROADCAST,RUNNING,SLAVE,MULTICAST>  mtu 1500
        ether 00:0d:3a:44:49:76  txqueuelen 1000  (Ethernet)
        RX packets 7588  bytes 777799 (759.5 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 31837  bytes 6119905 (5.8 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 2  bytes 176 (176.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 2  bytes 176 (176.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```

# 6. Show that forward and reverse host lookups are correctly resolved

Below the execution of the getent command
```
[root@node05 ~]# getent hosts localhost node05 node01 node02 node03
::1             localhost localhost.localdomain localhost6 localhost6.localdomain6
fe80::20d:3aff:fe44:4976 node05
10.0.1.13       node01.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net node01
10.0.1.14       node02.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net node02
10.0.1.15       node03.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net node03
[root@node05 ~]#
```

The hosts file, it is equals in the all nodes (node05,node01,node02,node03)
```
[root@node05 ~]# more /etc/hosts
127.0.0.1   localhost localhost.localdomain localhost4 localhost4.localdomain4
::1         localhost localhost.localdomain localhost6 localhost6.localdomain6
10.0.1.12 node05.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net node05
10.0.1.13 node01.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net node01
10.0.1.14 node02.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net node02
10.0.1.15 node03.d5ezrrashaturo4lzvyev1ruja.ax.internal.cloudapp.net node03
```

# 7. Show the nscd service is running

the service is installed,started and enabled in the all nodes

```
[root@node05 ~]# systemctl status nscd
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2019-02-11 13:42:36 UTC; 20s ago
  Process: 31123 ExecStart=/usr/sbin/nscd $NSCD_OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 31124 (nscd)
   CGroup: /system.slice/nscd.service
           └─31124 /usr/sbin/nscd
[root@node05 ~]# systemctl enable nscd
```
# 8. Show the ntpd service is running

the service is installed,started and enabled in the all nodes


```
[root@node05 ~]# systemctl status ntpd
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; enabled; vendor preset: disabled)
   Active: active (running) since Mon 2019-02-11 13:45:17 UTC; 18s ago
  Process: 31262 ExecStart=/usr/sbin/ntpd -u ntp:ntp $OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 31263 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─31263 /usr/sbin/ntpd -u ntp:ntp -g
[root@node05 ~]# systemctl enable ntpd
```

