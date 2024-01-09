## Implementing a business website using NFS for the backend file storage

1. Spin new EC2 with RHEL linux 9 OS

*** Previous experience LVM (implementing wordpress) was used to prepare the volumes. Limited screen shot taken

Create volume and attach to the NFS server
![](img/01.volumeAttached.png)

Partition the block volume using gdisk

![](img/2.partition.png)

Install lvm2

mark the partition volume as physical volumes(PVs)
![](img/3.pvs.png)

Add the 3 PVs to a volume group
![](img/4.vg.png)

create 3 logical group
1. lv-apps
2. lv-opt
3. lv-logs

![](img/5.lvcreate.png)

format the logical volumes and mount on /mnt
![](img/6.mount.png)

![](img/7.final_df-h.png)

## Install NFS server

1. install NFS server on the EC2instance with the attched prepared volumes

![](img/9.installnfs.png)

2. grant permission that will allow the webservers to read, write and execute files

3. configure access to NFS for client within the same subnet

![](img/10.chown.png)

4. configure the export file

![](img/11.export.png)

5. configure inbound traffic to allow NFS traffic from devices within the subnet

![](img/12.inbound.png)

## Install MySQL

1. Install mysql on the NFS server
![](img/13.installmysql.png)

2. create db name tooling and grant permission to `webaccess` on tooling db
![](img/14.mysqlconf.png)

## Webserver

#### Install NFS client
1. spin 2 EC2 instances
2. install nfs client
`sudo yum install nfs-utils nfs4-acl-tools -y
`
![](img/15.webserver1_nfs.png)

3. create a folder `/var/www` and mount it on /mnt/apps
`sudo mkdir /var/www
sudo mount -t nfs -o rw,nosuid <NFS-Server-Private-IP-Address>:/mnt/apps /var/www
`
![](img/16.mount_nfs_webserver.png) 

![](img/17.df.png)
4. persist the mount by modifying the record on `/etc/fstab`
with `<NFS-Server-Private-IP-Address>:/mnt/apps /var/www nfs defaults 0 0
`
![](img/18.fstab.png)

#### Install apache and php

1. install `sudo yum install httpd -y

sudo dnf install https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm

sudo dnf install dnf-utils http://rpms.remirepo.net/enterprise/remi-release-8.rpm

sudo dnf module reset php

sudo dnf module enable php:remi-7.4

sudo dnf install php php-opcache php-gd php-curl php-mysqlnd

sudo systemctl start php-fpm

sudo systemctl enable php-fpm

setsebool -P httpd_execmem 1`

![](img/19.installHttpd.png)

***** the above steps was duplicated on another systen

![](img/20.instances.png)

##### web server 2
![](img/22.server2.png)

webserver1 and 2 have /var/www/ pulling from the same nfs server

![](img/23.testA.png)
![](img/23.testB.png)

![](img/24.github.png)

Fork the tooling source code from darey.io github account
![](img/26.cloneGit.png)

![](img/24.github.png)

Open tcp port 80 on the web server

check security permission

![](img/25.selinux.png)

Update the db with `tooling-db.sql` script

![](img/27.sqlInsert.png)

Update the `functions.php` to connect to the db

![](img/28.dbconnect.png)

Insert a new username to login

![](img/30.adminaccount.png)

Open the `<webserver-url>/index.php, and login with the username: admin , password: admin

![](img/29.final.png)



