* Cloud provider 

Azure

* Virtual machine list
```
10.0.1.4 gateway.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net
10.0.1.5 master.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net
10.0.1.6 worker01.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net
10.0.1.7 worker02.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net
10.0.1.8 worker03.dvntjzkui45unfw1spn5i3dzca.ax.internal.cloudapp.net
```
* Linux release 

CentOS Linux release 7.5.1804 (Core)

* List the file system capacity for the first node
```
[root@gateway ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/sda2        30G  1.3G   29G   5% /
devtmpfs        7.9G     0  7.9G   0% /dev
tmpfs           7.9G     0  7.9G   0% /dev/shm
tmpfs           7.9G  9.3M  7.9G   1% /run
tmpfs           7.9G     0  7.9G   0% /sys/fs/cgroup
/dev/sdc       1023G   33M 1023G   1% /data
/dev/sda1       497M   81M  417M  17% /boot
/dev/sdb1        32G   49M   30G   1% /mnt/resource
tmpfs           1.6G     0  1.6G   0% /run/user/1000
```
* List the command and output for `yum repolist enabled`
```
[root@gateway ~]# yum repolist enabled
Loaded plugins: fastestmirror, langpacks
Loading mirror speeds from cached hostfile
repo id                  repo name                                      status
!base/7/x86_64           CentOS-7 - Base                                10,019
!extras/7/x86_64         CentOS-7 - Extras                                 364
!openlogic/7/x86_64      CentOS-7 - openlogic packages for x86_64          121
!updates/7/x86_64        CentOS-7 - Updates                              1,067
repolist: 11,571
```
* List the `/etc/passwd` entries for rocky and denali
```
rocky:x:3800:3800::/home/rocky:/bin/bash
denali:x:3900:3900::/home/denali:/bin/bash
```
* List the `/etc/group` entries for alaska and colorado
```
alaska:x:3901:denali
colorado:x:3902:rocky
```
* List the output of the following commands
  * `getent group alaska`
  * `getent passwd rocky`
```
[root@worker01 ~]# getent group alaska
alaska:x:3901:denali
[root@worker01 ~]# getent passwd rocky
rocky:x:3800:3800::/home/rocky:/bin/bash
```


