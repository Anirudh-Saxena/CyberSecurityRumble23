
PW*Challenge name : CLASSY*
Category : EASY
Tags : pwn|bby

https://ctf.cybersecurityrumble.de/problem/Classy

DESCRIPTION of the chal : 

Not everyone can be sophisicated enough to get a flag. Can you?
nc rumble.host 9797

below this there was the source code of the problem a cpp file : 

After going through the source code we can see that 


![Screenshot_2023-07-10_02_25_12](https://github.com/Anirudh-Saxena/CyberSecurityRumble23/assets/73027020/c083e62a-6ad0-4efe-9f4c-54716c22c5d3)

If your level is 2 and you know the password then only they will provide you flag by talking about the flag 
In the program there was a hardcoded password, but unfortunately that was the wrong password :) 

So lets start out rev eng process : 
* For this we will be using the gdb commands : 
first we will run the program using ./<nameofthefile>
to see how the program works : 
_$ ./classy      
What is your Connoisseur level?
1 
What do you want to talk about?
[1] Wine
[2] Cheese
[3] Flags
[4] I think I know enough now to be a higher level.
4
What is your Connoisseur level?
2
Please provide the password:
notknownyet
Wrong password.
What is your Connoisseur level?_

That's how the program works ☝☝


Now lets use the gdb tool :
1. Lets get inside the program by typing the following command :
`gdb classy`
2. Run the code using 'r' and make sure to interrupt the program by pressing `ctrl+c`
3. Now use the command : 
` print password or p password`
for printing the password the whole process will look something like this:
![Screenshot_2023-07-10_02_47_29](https://github.com/Anirudh-Saxena/CyberSecurityRumble23/assets/73027020/b5606ed1-4a3f-4b51-b3fe-c2455aea867a)

Now we have the password as : `55aefb4ca5630cc73a981e9d642324fc`
After getting the password connect the server using command `nc rumble.host 9797 ` and enter this password to get the flag 
![Screenshot_2023-07-10_02_52_38](https://github.com/Anirudh-Saxena/CyberSecurityRumble23/assets/73027020/816d18c3-05c4-4daf-abf7-643adfc9522a)

_if you want to learn more about the usage of gdb in cpp follow this link : 
https://www.geeksforgeeks.org/gdb-command-in-linux-with-examples/_
