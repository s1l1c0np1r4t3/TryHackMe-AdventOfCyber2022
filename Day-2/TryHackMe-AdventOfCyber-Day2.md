<img width="600" src="https://user-images.githubusercontent.com/56886006/207661596-f8ed4e39-93e9-4b24-ba68-0d2fade203e0.png">

---

Follow me on twitter to stay updated! [Twitter @s1l1c0np1r4t3x](https://twitter.com/s1l1c0np1r4t3x)

Or get all my links here: [Linktree @s1l1c0np1r4t3](https://linktr.ee/s1l1c0np1r4t3)

---

<img width="500" src="https://user-images.githubusercontent.com/56886006/208248963-4066cfef-636e-4f7c-97a8-23cce87a2f95.png">

# Day 2
Link to CTF: https://tryhackme.com/christmas

## Description/Debrief

Santa’s Security Operations Center (SSOC) has noticed one of their web servers, santagift.shop has been hijacked by the Bandit Yeti APT group. Elf McBlue’s task is to analyse the log files captured from the web server to understand what is happening and track down the Bandit Yeti APT group.

---


# Objectives

## Learning Objectives:

In today’s task, you will:
<ul>
<li>Learn what log files are and why they’re useful.</li>
<li>Understand what valuable information log files can contain.</li>
<li>Understand some common locations these logs file can be found.</li>
<li>Use some basic Linux commands to start analysing log files for valuable information.</li>
<li>Help Elf McBlue track down the Bandit Yeti APT!</li>
</ul>    


## What Are Log Files and Why Are They Useful

Log files are files that contain historical records of events and other data from an application. Some common examples of events that you may find in a log file:

<ul>
<li>Login attempts or failures.</li>
<li>Traffic on a network.</li>
<li>Things (website URLs, files, etc.) that have been accessed.</li>
<li>Password changes.</li>
<li>Application errors (used in debugging).</li>
<li>and many, many more.</li>
</ul>    

By making a historical record of events that have happened, log files are extremely important pieces of evidence when investigating:

<ul>
<li>What has happened?</li>
<li>When has it happened?</li>
<li>Where has it happened?</li>
<li>Who did it? Were they successful?</li>
<li>What is the result of this action?</li>
</ul>    

    
## Practical:

For today's task, you will need to deploy the machine attached to this task by pressing the green "Start Machine" button located at the top-right of this task. The machine should launch in a split-screen view. If it does not, you will need to press the blue "Show Split Screen" button near the top-right of this page.    
    
Use the knowledge you have gained in today's task to help Elf McBlue track down the Bandit Yeti APT by answering the questions below.


<img width="500" src="https://user-images.githubusercontent.com/56886006/208249000-f2934fe9-37ce-4080-af01-4dfd18e7b891.png">
    
I started up the AttackBox and got to work!

<img width="500" src="https://user-images.githubusercontent.com/56886006/208248979-90f6abc5-85bf-4e22-afa4-f8c5fd0f7a85.png">

Command:

`ssh elfmcblue@10.10.22.162`

<img width="500" src="https://user-images.githubusercontent.com/56886006/208249015-3492f9f6-71ed-4fbc-832a-22a52b64ee50.png">

Command:

`ls`

<img width="500" src="https://user-images.githubusercontent.com/56886006/208249018-5d0b6830-a198-4fbb-9696-0a9d10687986.png">

Command:

`nano webserver.log`

<img width="500" src="https://user-images.githubusercontent.com/56886006/208249025-2929fa34-a4e3-4163-9c3d-18ef1e5c2c24.png">

There is a lot of information here and more than likely too many pages for us to all go through and analyze ourselves. I wanted to break everything down and get an idea of how many different IP's have connected to the compromised machine recently. I used a command to get a list of all of the unique IP's in the log file.

Command:

`grep -o "[0-9]\+\.[0-9]\+\.[0-9]\+\.[0-9]\+" webserver.log | sort | uniq`

This sorted all of the different IP address for me and gave me only unique ones.

This is what it returned:

<img width="500" src="https://user-images.githubusercontent.com/56886006/208249042-5dbef15a-d2ef-41b3-b081-00278c882829.png">

There are four unqie IP addresses that have connected to Santa's machine according to the log files.

They are:

`10.10.249.191`

`10.10.60.160`

`10.9.12.30`

`107.0.0.0`

Keeping these IP addresses in mind I decided to start looking for the Santa list that was stolen and try to see which of these IPs accessed it and downloaded it.

Command:

`grep -i "santa" webserver.log`

<img width="500" src="https://user-images.githubusercontent.com/56886006/208249060-39183bcf-2e58-4d28-bbd6-afccf07fc930.png">
    
As you can see there is a lot there.

However there is one specific instance in which Santa's list was accessed.
    
<img width="500" src="https://user-images.githubusercontent.com/56886006/208249068-b3090f1c-7198-41f0-803b-f39bd18d2afa.png">

This is also an answer to another one the questions on HTB. The date in which Santa's naughty and nice list was stolen. 
    
`[18/Nov/2022:12:34:39 +0000]`

That would mean the list was stolen on November 18th, 2022. A quick calendar check makes that a Friday. Giving another answer for HTB.

Also making the IP of attacker:

`10.10.249.191`

The important list that was stolen from Santa was:

`santaslist.txt`

Now that I had the answer for all of the questions it was time to find the HTB flag within the log files.

I chose to use the known used format for the flag HTB{} to search for the flag. I started with the file we have already been working in, the webserver.log

`grep "THM" webserver.log` 
    
<img width="500" src="https://user-images.githubusercontent.com/56886006/208249079-789e55a1-2d1f-470f-b4cf-fc43ff8c71bd.png">    
    
No luck, I did the same for the SSH log.

`grep "THM" SSHD.log`
    
<img width="500" src="https://user-images.githubusercontent.com/56886006/208249094-40bc6c85-d953-49a1-9247-15345eecdf03.png">     

SUCCESS!  

We found the flag!

`THM{***************}`
  
<img width="500" src="https://user-images.githubusercontent.com/56886006/208249114-18c6721e-169c-460d-b544-079d54162d46.png"> 


h4ppy hunt1ng!    
    
s1l1c0np1r4t3
