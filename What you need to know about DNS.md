# What you need to know about DNS

From an Ip address to a web address :

196.132.63.21  -> blablabla.com


## Domain hierarchy

https://assets.tryhackme.com/additional/dnsindetail/domain_levels.png

### a. Top-Level Domain

There are two types of TLD, gTLD (Generic Top Level) - .com .org - and ccTLD (Country Code Top Level Domain) - .ca .be .fr -. Full list here : https://data.iana.org/TLD/tlds-alpha-by-domain.txt

### b. Second-Level Domain

The second-level domain is limited to 63 characters + the TLD and can only use a-z 0-9 and hyphens (cannot start or end with hyphens or have consecutive hyphens). in bold, you can find an example of SLD : www.<b>jeuxvideo</b>.com

### c. Subdomain

A subdomain sits on the left-hand side of the Second-Level Domain using a period to separate it; for example, in the name admin.tryhackme.com the admin part is the subdomain. A subdomain name has the same creation restrictions as a SLD, being limited to 63 characters and can only use a-z 0-9 and hyphens (cannot start or end with hyphens or have consecutive hyphens). You can use <b>multiple subdomains</b> split with periods to create longer names, such as jupiter.servers.tryhackme.com. But the length must be kept to 253 characters or less. There is no limit to the number of subdomains you can create for your domain name.


## Record types

Have a look at this link for complete list explained : https://phoenixnap.com/kb/dns-record-types#ftoc-heading-15


