### Example

To get all the directories of a website
<BR>
gobuster -u http://jewel.uploadvulns.thm dir --wordlist /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
<BR>

To get all the files of a specific directory
<BR>
gobuster -u http://jewel.uploadvulns.thm/content/ dir -x jpg --wordlist ~/Downloads/UploadVulnsWordlist.txt
<BR>
