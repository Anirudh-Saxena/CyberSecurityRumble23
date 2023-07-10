**Challenge name : ChapGPyT**
Challenge type : Easy web

Descritpion of challenge : I've made ChatGPT implemented a challenge. I hope you can solve this verry hard challenge

Page link : http://chatgpyt.rumble.host/ _might not be active_

So lets start solving the challenge using brupsuite :

I am using foxyproxy for the proxy connection with the burpsuite so that all the traffic on the site can be checked using burpsuite 

![Screenshot_2023-07-10_03_37_33](https://github.com/Anirudh-Saxena/CyberSecurityRumble23/assets/73027020/78a7f5b7-e8b3-4665-adb1-ddd0cec72630)

As we can see that the website is using GET request in the first step

After forwading the request we are able to see a POST request , so basically site works with only two request parameters here that are GET and POST 
now we have the task to find the vuln on the basis of these information only lets see what are the requests that are being forwarded by the burpsuite.

By pressing `ctrl+r` we can send the reponses to the repeater so that we can try different inputs on it.

![Screenshot_2023-07-10_03_48_22](https://github.com/Anirudh-Saxena/CyberSecurityRumble23/assets/73027020/50a75320-040b-4a59-8445-be5ce7bd6b4c)

hmm this in intresting 
_330e3e3bbab7a08e48520cb696840294_ : this in nothing but a mb5 string so basically site is converting our messages to md5 string while interpreting it 

now we have to send the get request and insert the value as 1 so that we can obtain the flag :
for that we will be using this website to convert 1 into md5
_https://www.md5hashgenerator.com/_

so 
our request will look something like this :
`GET /get_message/c4ca4238a0b923820dcc509a6f75849b HTTP/1.1`
![Screenshot_2023-07-10_03_55_34](https://github.com/Anirudh-Saxena/CyberSecurityRumble23/assets/73027020/2870eece-bd28-41c4-80d1-84d5f2abb8ed)

and here is your flag!!

`CSR{GrindingChatGPTUntilItGivesYOuAChallangeLol}`


_in order to learn more about get and post 
follo this link
https://www.w3schools.com/tags/ref_httpmethods.asp_
