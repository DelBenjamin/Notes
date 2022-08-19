# How to Nmap

Every computer has a total of 65535 available ports. But, in general, we tend to focus on the first 1024, wich are labelled "well-known".

Here is a few options with Nmap : 

- -O 	= the operating system of the target
- -v or vv	 = verbosity of the nmap reports
- -A 	= "aggressive mode" : activates service detection, operating system detection, a traceroute and common script scanning.
- -p [number] 	= scan a specific ports
- -p [number]-[number] 	= scan a range of specific ports
- -p- 	= Scan ALL ports

## Syntax : 

-> nmap -option1 -option2 [target IP]

## Sources : 

Tryhackme, Nmap : https://tryhackme.com/room/furthernmap
