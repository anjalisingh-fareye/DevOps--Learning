# Linux Day 3

## Topics Covered

1. Linux File System Permissions
2. ACL (Access Control List)
3. Find Command
4. Word Count
5. Job Automation
6. Sudo and Sudo Group
7. Network Configuration using nmcli
8. Grep Command

## Hands-on Practice

Practiced Linux permissions, ACL configuration, file searching,
word counting, cron job automation, sudo access, network
configuration using nmcli, and text searching using grep.


# Linux File Permissions

## Check Permissions

ls -l

## Change Permissions

chmod 755 file.txt
chmod 644 file.txt
chmod +x script.sh

## Change Ownership

chown user file.txt
chown user:group file.txt
chgrp group file.txt

## Permission Types

r = Read
w = Write
x = Execute

# ACL

## Check ACL

getfacl file.txt

## Add User Permission

setfacl -m u:username:rwx file.txt

## Add Group Permission

setfacl -m g:groupname:rwx file.txt

## Remove User ACL

setfacl -x u:username file.txt

## Remove All ACL

setfacl -b file.txt

# Find Command

find . -type f
find . -type d
find . -name "file.txt"
find . -name "*.txt"
find /home -type f
find . -size +10M
find . -user username

# Word Count

wc file.txt
wc -l file.txt
wc -w file.txt
wc -m file.txt
wc -c file.txt

# Job Automation

## Check Cron Jobs

crontab -l

## Edit Cron Jobs

crontab -e

## Example
echo "Linux Practice" >> /tmp/test.log

# Sudo and Sudo Group

sudo -l
sudo -i

## Add User to Sudo Group

sudo usermod -aG sudo username

## Check Groups

groups username

# Network Configuration using nmcli

nmcli general status
nmcli device status
nmcli connection show
nmcli device show
nmcli device wifi list

## Activate Connection

sudo nmcli connection up "connection-name"

## Deactivate Connection

sudo nmcli connection down "connection-name"

# nmcli

nmcli (NetworkManager Command Line Interface) is used to
manage and configure network connections from the Linux
command line.

## Commands

nmcli general status
nmcli device status
nmcli connection show
nmcli device show
nmcli device wifi list
nmcli connection up "connection-name"
nmcli connection down "connection-name"

# Grep

# Grep Command

grep is used to search for specific text or patterns inside files.

## Commands

grep "Linux" file.txt
grep -i "linux" file.txt
grep -n "Linux" file.txt
grep -c "Linux" file.txt
grep -v "Linux" file.txt
grep -w "Linux" file.txt
grep -r "Linux" .
grep -E "Linux|Unix" file.txt


15-Aug-2026/
│── README.md
│── health.sh
│── notes.md
│── commands.txt
health.sh
CPU Utilization
Memory Utilization
Disk Utilization
Running Processes
Permission Check
Alert Condition (40%)
commands.txt
touch
nano
chmod +x
bash
top
free
df -h
ps -e
wc -l
grep
awk
cut
echo
if
notes.md
