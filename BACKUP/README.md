Challenge name : **BACKUP**
Challenge Type : misc | bby | cry

Challenge des:
This company has an interesting approach to backuping their routers. I sniffed the network traffic while they conducted a backup. 
Check if you find something interesting.

Author: rugo

file : _https://files.rumble.host/backup.tar.gz_

This was a easy challenge , so in this challenge we first have to donwload and extract the file then we can see that there is a pcap file which can be accessdd 
using wireshark tool 

![image](https://github.com/Anirudh-Saxena/CyberSecurityRumble23/assets/73027020/e51650fd-b7da-4ca3-824c-a77cf6e29b8d)

Upon opening the file you can see the packet transfer list :
![image](https://github.com/Anirudh-Saxena/CyberSecurityRumble23/assets/73027020/7fb26c47-b93b-42d6-b48f-ca6b3dd58da0)

Now lets look for some useful content :

By scrolling and looking through the file we can see that there is a log which says a file with name backup is being tranfered so out aim will be to retrieve that file :
For viewing in this view we have to right click on the packet 
and then _click on the follow : TCP STREAM_
![image](https://github.com/Anirudh-Saxena/CyberSecurityRumble23/assets/73027020/b3cd9234-408b-43b5-9aa2-73c902089bc7)

in order to retrieve  the file we have go through the following steps :

1. Click on File
![image](https://github.com/Anirudh-Saxena/CyberSecurityRumble23/assets/73027020/4cc0bdcb-4a35-43ae-a7fc-66090e76e7be)
2. Click on **Export objects -> FTP DATA**
![image](https://github.com/Anirudh-Saxena/CyberSecurityRumble23/assets/73027020/f2944e81-12a0-43b6-92bd-cd452e22ef79)
3. Now click on save the file

Now upon clicking the backupfolder we can see that it contains a json file which is protected using password ,
Now our next aim is to find the password , 
lets again look at the packets :
![image](https://github.com/Anirudh-Saxena/CyberSecurityRumble23/assets/73027020/981b978a-9de0-4e25-84db-48c722dfe345)
Do the following process for  any packet  then you will see something like this

![image](https://github.com/Anirudh-Saxena/CyberSecurityRumble23/assets/73027020/6083c547-058c-4935-9427-9534cd1c661f)
Here we can see the password that we have to use in order to unlock the file copy the `pass : sup3rs3cur3`

and there you have the flag : 
` { "masterkey": "flag{TelnetAndFTPAreSoVErySecure}" }`
![image](https://github.com/Anirudh-Saxena/CyberSecurityRumble23/assets/73027020/9d51fade-fd84-4bdb-bb8b-0100ec41b645)

