# Upload Vulnerabilities

This is the write up for the room Upload Vulnerabilities on Tryhackme and it is part of the Web Fundamentals Path
<!--more-->

# Upload Vulnerabilities
> Room link: https://tryhackme.com/room/uploadvulns

> Tools used:
> * Burpsuite
> * gobuster
> * Wappalyser

## Task 1 Getting Started 
Let's deploy the machine to give it a few minutes to boot.
click on the `Start Machine` button.
now you have to configure your own pc.

open host file
* on linux  /etc/hosts
* on windows C:\Windows\System32\drivers\etc\hosts

## Task 2 Introduction
The purpose of this room to explore some of the vulnerabilities resulting from improper handling of file uploads.
We will be looking at:
 * Overwriting existing files on a server
 * Uploading and Executing Shells on a server
 * Bypassing Client-Side filtering
 * Bypassing various kinds of Server-Side filtering
 * Fooling content type validation checks

## Task 3 General Methodology 

## Task 4 Overwriting Existing Files 

{{< figure src="/posts/Cyber-Security/upload vulnerabilities/warning.png" >}}

{{< figure src="https://i.imgur.com/7KmsrTW.png" >}}

{{< figure src="https://i.imgur.com/BeqAZ3s.png" >}}

{{< figure src="https://i.imgur.com/8PiIuiu.png" >}}

{{< figure src="https://i.imgur.com/TIoA2DR.png" >}}


{{< admonition type=abstract title="Answer the questions below" open=false >}}
1. What is the name of the image file which can be overwritten?

    Ans: `mountains.jpg`

2. Overwrite the image. What is the flag you receive?

    Ans: `THM{OTBiODQ3YmNjYWZhM2UyMmYzZDNiZjI5}`
{{< /admonition >}}

