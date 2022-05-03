# linux-cmds

__________________________________________________________________________________________________

#### copy serched files with ls,cp and grep command

```bash
ls | grep .mp3 | xargs -I '{}' cp '{}' /home/user
```
here `.mp3` is the search term you can specify `date` or `name` and `/home/user` is the paste location

__________________________________________________________________________________________________

#### Run the previous command with sudo previlage
``` bash
sudo !!
```
here `!!` is the operator which is used for pick up the last command you enterd
also you can make this command as dynamic as you want like this

```
docker
sudo !! ps
```

__________________________________________________________________________________________________

#### Count the result

``` bash
ls | grep .mp3 | wc -l
```

__________________________________________________________________________________________________
#### Git clone with ssh Key

``` bash
ssh-agent bash -c 'ssh-add /your-key-path; git clone git@github.com:user/project.git'
```

__________________________________________________________________________________________________

#### Copy Files over servers 

``` bash
scp -r <file> user@<new_server_ip>:<dest_path_path>

```

__________________________________________________________________________________________________

#### Host file location windows

``` bash
C:\Windows\System32\drivers\etc\hosts
```
__________________________________________________________________________________________________
#### Host file location linux

``` bash
/etc/hosts
```

__________________________________________________________________________________________________

#### Check the os linux

``` bash
cat /etc/os-release
```
__________________________________________________________________________________________________

 #### Open the ports in the firewall and iptables

``` bash
firewall-cmd --zone=public --permanent --add-port {port}/tcp
firewal-cmd --reload
```
__________________________________________________________________________________________________

#### Start the service for system reboot 
``` bash
systemctl enable <Service Name>
```
__________________________________________________________________________________________________

#### Vim seach and replace all
``` bash
:%s/foo/bar
:%s/foo/bar/gc
```
__________________________________________________________________________________________________

 #### IBM Cloud Password 

``` bash
ibmcloud login --sso

ibmcloud plugin install vpc-infrastructure

ibmcloud is instance-initialization-values <INSTANCE_ID> --private-key @<PRIVATE_KEY>
```
_______________________________________________________________________________________________

 #### Git clone in specific branch 


``` bash
git clone -b <branch> <remote_repo>
```
_______________________________________________________________________________________________

 #### Fetch the file from the sftp server 

``` bash

sftp {user}@{ip}:{file_location}

expl - sftp igor@10.204.68.51:/mnt/sftp_share/test.txt
```

_________________________________________________________________________________________________

#### JQ for terminal


for fetch the values from the JSON file using terminal 
``` bash
jq '.data.id' file.json

use -r for remove the double quotes

jq -r '.data.id' file.json
```
_________________________________________________________________________________________________

 #### lsscsi Server commands

``` bash
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
```

_______________________________________________________________________________________________


#### You have multiple ways to set : as the separator:
``` bash
awk -F: '{print $1}'

awk -v FS=: '{print $1}'

awk '{print $1}' FS=:

awk 'BEGIN{FS=":"} {print $1}'
```
_______________________________________________________________________________________________

#### Unmount busy device forcefully
``` bash
umount -l /PATH/OF/BUSY-DEVICE
umount -f /PATH/OF/BUSY-NFS (NETWORK-FILE-SYSTEM)
```
_______________________________________________________________________________________________

#### Check the architecture of linux

``` bash
arch
echo $(arch)
```
_______________________________________________________________________________________________

#### Color schemes for terminal

> you must git the `-e` with echo to see the color changes
 ``` bash
 
#!/bin/bash

# Color variables
red='\033[0;31m'
green='\033[0;32m'
yellow='\033[0;33m'
blue='\033[0;34m'
magenta='\033[0;35m'
cyan='\033[0;36m'
# Clear the color after that
clear='\033[0m'

# Examples

echo -e "The color is: ${red}red${clear}!"
echo -e "The color is: ${green}green${clear}!"
echo -e "The color is: ${yellow}yellow${clear}!"
echo -e "The color is: ${blue}blue${clear}!"
echo -e "The color is: ${magenta}magenta${clear}!"
echo -e "The color is: ${cyan}cyan${clear}!"

echo -e '\033[0;31m Nitin \033[0m'
 
 ```
_______________________________________________________________________________________________

#### Getting time in bash using the diffent styles

``` bash
Parameter
Output
date +”%m/%d/%Y”
03/25/2019
date +”%d-%b-%Y”
25-Mar-2019
date +”%Y %b %m”
2019 Mar 25
date +”%H:%M”
14:40
date +”%I:%M %p”
02:40 PM
date +”%H:%M:%S”
14:40:32
date +”%I:%M:%S %p”
02:40:32 PM
date +”%m/%d/%Y %H:%M”
03/25/2019 14:40
date +”%A, %m %d %Y %H:%M”
Monday, 03 25 2019 14:40
date +”%A, %b %d, %Y %I:%M %p”
Monday, Mar 25, 2019 02:40 PM
date +”%A, %b %d, %Y %H:%M:%S”
Monday, Mar 25, 2019 14:40:32

```
