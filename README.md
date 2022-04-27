# linux-cmds

 Copy Files over servers 

 > scp -r <file> user@<new_server_ip>:<dest_path_path>


__________________________________________________________________________________________________

Host file location windows


> C:\Windows\System32\drivers\etc\hosts

__________________________________________________________________________________________________

 open the ports in the firewall and iptables


> firewall-cmd --zone=public --permanent --add-port 9102/tcp
> firewal-cmd --reload

__________________________________________________________________________________________________


start the service for system reboot 

> systemctl enable <Service Name>

__________________________________________________________________________________________________


Vim seach and replace all
  
> :%s/foo/bar
> :%s/foo/bar/gc

__________________________________________________________________________________________________


 IBM Cloud Password 


> ibmcloud login --sso

> ibmcloud plugin install vpc-infrastructure

> ibmcloud is instance-initialization-values <INSTANCE_ID> --private-key @<PRIVATE_KEY>

_______________________________________________________________________________________________

  Git clone in specific branch 



> git clone -b <branch> <remote_repo>

_______________________________________________________________________________________________

 fetch the file from the sftp server 



> sftp {user}@{ip}:{file_location}

> expl - sftp igor@10.204.68.51:/mnt/sftp_share/test.txt


_________________________________________________________________________________________________

JQ for terminal


for fetch the values from the JSON file using terminal 

>  jq '.data.id' file.json

use -r for remove the double quotes

>  jq -r '.data.id' file.json

_________________________________________________________________________________________________

 lsscsi Server commands


> sg_map -i

1. To list SCSi devices:

> lsscsi

2. To get the classic output:

> lsscsi -c
> lsscsi --classic

3. To get the device name the device node major and minor numbers:

> lsscsi -d
> lsscsi --device

4. To output the scsi generic device file name:

> lsscsi -g
> lsscsi --generic

5. To get the help:

> lsscsi -h
> lsscsi --help

6. To list the SCSI hosts currently attached to the system.

> lsscsi -H
> lsscsi --hosts

7. To Use linux default algorithm for naming devices:

> lsscsi -k
> lsscsi --kname

8. To output additional information in pairs:

> lscsci -L
> lscsci --list

9. To output additional information for each SCSI device:

> lsscsi -l
> lsscsi --long

10. To output additional data integrity (protection) information:

> lsscsi -p
> lsscsi --protection

11. To output transport information:

> lsscsi -t
> lsscsi --transport

12. To get the verbose info:

> lsscsi -v
> lsscsi --verbose

13. To get the version:

> lsscsi -V
> lsscsi --version

14. To assumes sysfs is mounted at PATH instead of the default /sys:

> lsscsi -y
> lsscsi --sysfsroot=PATH


_______________________________________________________________________________________________


You have multiple ways to set : as the separator:

> awk -F: '{print $1}'

> awk -v FS=: '{print $1}'

> awk '{print $1}' FS=:

> awk 'BEGIN{FS=":"} {print $1}'

_______________________________________________________________________________________________


Unmount busy device forcefully


> umount -l /PATH/OF/BUSY-DEVICE
> umount -f /PATH/OF/BUSY-NFS (NETWORK-FILE-SYSTEM)

_______________________________________________________________________________________________

check the architecture of linux


> arch

OR

> echo $(arch)

_______________________________________________________________________________________________



