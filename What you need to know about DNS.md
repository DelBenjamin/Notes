# What you need to know about DNS

From an Ip address to a web address :

196.132.63.21  -> blablabla.com


## Domain hierarchy

https://assets.tryhackme.com/additional/dnsindetail/domain_levels.png

### a. Top-Level Domain

There are two types of TLD, gTLD (Generic Top Level) - .com .org - and ccTLD (Country Code Top Level Domain) - .ca .be .fr -. Full list here : https://data.iana.org/TLD/tlds-alpha-by-domain.txt

### b. Second-Level Domain

The second-level domain is limited to 63 characters + the TLD and can only use a-z 0-9 and hyphens (cannot start or end with hyphens or have consecutive hyphens). in bold, you can find an example of SLD : www.<b>jeuxvideo</b>.com
