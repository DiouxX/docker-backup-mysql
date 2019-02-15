# docker-backup-mysql

## Description
This script allow to backup a MySQL database who run on docker and
if you want to copy local DUMP on a remote server

## Usage

Script usage :


	Display help

-c	Mysql/Mariadb container name

-d	Database name

-n	Backup name (By default : Database name + YYYY-MM-DD-HMS)

-f	Local backup folder

-t	Remote Backup Path

-k	Keep local backup if enable transfert option

-P	SSH Remote Port (default : 22)

-v	Verbose mode

## Example

If you want a remote DUMP
```sh
docker_backup_mysql -c mysql-docker -d glpidb -n glpi-backup -t root@192.168.1.1:/mnt/backup_server/backup_mysql/glpi/
```

If you want a local DUMP
```sh
docker_backup_mysql -c mysql-docker -d glpidb -n glpi-backup -f /opt/backup/glpi/
```

*********
IMPORTANT
*********

Don't forget to copy your public SSH key on remote server ( To automate backup task )

[user@ordi ~]$ ssh-copy-id -i ~/.ssh/id_rsa.pub user@remote-server
