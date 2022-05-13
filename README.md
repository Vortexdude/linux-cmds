# linux-cmds

__________________________________________________________________________________________________

#### copy serched files with ls,cp and grep command

```bash
ls | grep .mp3 | xargs -I '{}' cp '{}' /home/user
```
> Here `.mp3` is the search term you can specify `date` or `name` and `/home/user` is the paste location you can also use for other opearions like `moving` or `deleing` the files

```bash
ls | grep .mp3 | xargs -I '{}' rm -rf '{}' /home/user

```
__________________________________________________________________________________________________

#### Run the previous command with sudo previlage
``` bash
sudo !!
```
> Here `!!` is the operator which is used for pick up the last command you enterd also you can make this command as dynamic as you want like this
> !! stands for fetch the previous command
```
docker
sudo !! ps
```
__________________________________________________________________________________________________

#### Fix a really long commd with text editor {last command}

```bash
fc
```
__________________________________________________________________________________________________
#### Run the bash script that is place into the github

``` bash
wget -O - https://raw.githubusercontent.com/<username>/<project>/<branch>/<path>/<file> | bash

```
So outputting to `-` will actually write the files content to `STDOUT` and then you simply pipe it to `bash` or whatever shell you prefer. If you script needs `sudo` rights you need to do `sudo bash` at the end so the line becomes:

``` bash
wget -O - https://raw.githubusercontent.com/<username>/<project>/<branch>/<path>/<file> | sudo bash

```

##### Give arguement to the file

``` bash
wget -O - https://raw.githubusercontent.com/<username>/<project>/<branch>/<path>/<file> | bash -s <arg>
```
##### Example

```
wget -O - https://raw.githubusercontent.com/vortexdude/src/main/script.sh | bash -s setup_role_dir

```
__________________________________________________________________________________________________
#### Run the any previous command with its number
> Run the history command and copy command number and put the *!* mark before the number 
``` bash
history
!123
```

__________________________________________________________________________________________________

#### Run VS code as sudo 
``` bash
sudo code --user-data-dir="~/.vscode-root"
```
__________________________________________________________________________________________________

#### Create folder structure
``` bash
mkdir -p /folder/{sub1,sub2}/{sub1,sub2,sub3}
```
> Here `-p` used for creating parent directories if dosen`t exist 

__________________________________________________________________________________________________

#### Exit the terminal but leave all procces runnig
``` bash
disown -a && exit
```
__________________________________________________________________________________________________

#### Mount the nfs server
``` bash
sudo apt update -y && sudo apt install nfs-common -y
mkdir -p /mnt/nfs
mount -t nfs 10.0.0.0:/mnt /mnt/nfs

```
> Here `10.0.0.0` is the ip that you have to mount and `/mnt` is the directory that is shared in that server and `/mnt/nfs` is the local directory 
__________________________________________________________________________________________________

#### Clean the output with no errors
``` bash
command 2>/dev/null
```
> Here `2` difines the standed erors wich are redirected to the `/dev/null` drectory this is file where all the data will be lost so that the erros are not apprearing on the terminal <br/>
> you can use this with any commands where you dont want to get any type of errors this is extremly useful in automation where you dont want to get the errors on the terminal
__________________________________________________________________________________________________
#### Count the result

``` bash
ls | grep .mp3 | wc -l
```
__________________________________________________________________________________________________

#### Redirect or append the standerd output into a file

for redirect the standerd output
```bash
ls >log.txt
```
for append the standerd output
``` bash
ls >>log.txt
```

__________________________________________________________________________________________________

#### Generate hashed password with openssh

``` bash
openssl passwrd -1 -salt name password
```
> Where `name` is apeended on the hashed form and `password` is actual password

__________________________________________________________________________________________________

#### RPCInfo for the nfs server or ther stats for the server

for localhost
```
rpcinfo -p 
```

for server
``` bash
rpcinfo -p <server_ip>
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

> you must add the `-e` with echo to see the color changes
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

 #### IBM Cloud Dcrypt Password  with ssh key

``` bash
ibmcloud login --sso

ibmcloud plugin install vpc-infrastructure

ibmcloud is instance-initialization-values <INSTANCE_ID> --private-key @<PRIVATE_KEY>
```
_______________________________________________________________________________________________
