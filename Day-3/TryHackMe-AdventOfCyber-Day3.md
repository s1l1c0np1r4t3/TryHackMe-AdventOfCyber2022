<img width="600" src="https://user-images.githubusercontent.com/56886006/207661596-f8ed4e39-93e9-4b24-ba68-0d2fade203e0.png">

---

Follow me on twitter to stay updated! [Twitter @s1l1c0np1r4t3x](https://twitter.com/s1l1c0np1r4t3x)

Or get all my links here: [Linktree @s1l1c0np1r4t3](https://linktr.ee/s1l1c0np1r4t3)

---

<img width="500" src="https://user-images.githubusercontent.com/56886006/208966279-fd5b2468-3fb5-4c82-86a2-083dd353a9d9.png">

# Day 3

Link to CTF: https://tryhackme.com/christmas

## Description/Debrief

As the elves are trying to recover the compromised `santagift.shop` website, elf Recon McRed is trying to figure out how it was compromised in the first place. Now we have to help him in gathering open-source information against the website. 

---

# Objectives

## Learning Objectives:

<ul>
<li>What is OSINT, and what techniques can extract useful information against a website or target?</li>
<li>Using dorks to find specific information on the Google search engine</li>
<li>Extracting hidden directories through the Robots.txt file</li>
<li>Domain owner information through WHOIS lookup</li>
<li>Searching data from hacked databases</li>
<li>Acquiring sensitive information from publicly available GitHub repositories</li>
</ul>

## What is OSINT
OSINT is gathering and analysing publicly available data for intelligence purposes, which includes information collected from the internet, mass media, specialist journals and research, photos, and geospatial information. The information can be accessed via the open internet (indexed by search engines), closed forums (not indexed by search engines) and even the deep and dark web. People tend to leave much information on the internet that is publicly available and later on results in impersonation, identity theft etc. 

## OSINT Techniques

### Google Dorks

Google Dorking involves using specialist search terms and advanced search operators to find results that are not usually displayed using regular search terms. You can use them to search specific file types, cached versions of a particular site, websites containing specific text etc.  Bad actors widely use it to locate website configuration files and loopholes left due to bad coding practices. Some of the widely used Google dorks are mentioned below: 

<ul>
<li>inurl: Searches for a specified text in all indexed URLs. For example, `inurl:hacking` will fetch all URLs containing the word "hacking".</li>
<li>filetype: Searches for specified file extensions. For example, `filetype:pdf "hacking"` will bring all pdf files containing the word "hacking".</li>
<li>site: Searches all the indexed URLs for the specified domain. For example, `site:tryhackme.com` will bring all the indexed URLs from `tryhackme.com`.</li>
<li>cache: Get the latest cached version by the Google search engine. For example, `cache:tryhackme.com`.</li>
</ul>


For example, you can use the dork `site:github.com "DB_PASSWORD"` to search only in `github.com` and look for the string `DB_PASSWORD` (possible database credentials). You can learn more about Google dorks through this free room.


### WHOIS Lookup

WHOIS database stores public domain information such as registrant (domain owner), administrative, billing and technical contacts in a centralised database. The database is publicly available for people to search against any domain and enables acquiring Personal Identifiable Information (PII) against a company, like an email address, mobile number etc., of technical contact. Bad actors can, later on, use the information for profiling, spear phishing campaigns (targeting selected individuals) etc. Nowadays, registrars offer Domain Privacy options that allow users to keep their WHOIS information private from the general public and only accessible to certain entities like designated registrars. 

Multiple websites allow checking the WHOIS information against the website. For example, you can check WHOIS information on `github.com` through this free website. 

### Robots.txt

The robots.txt is a publicly accessible file created by the website administrator and intended for search engines to allow or disallow indexing of the website's URLs. All websites have their robots.txt file directly accessible through the domain's main URL. It is a kind of communication mechanism between websites and search engine crawlers. Since the file is publicly accessible, it doesn't mean anyone can edit or modify it. You can access robots.txt by simply appending robots.txt at the end of the website URL. For example, in the case of Google, we can access the robots.txt file by clicking this URL.

### Breached Database Search

Major social media and tech giants have suffered data breaches in the past.  As a result, the leaked data is publicly available and, most of the time contains PII like usernames, email addresses, mobile numbers and even passwords. Users may use the same password across all the websites; that enables bad actors to re-use the same password against a user on a different platform for a complete account takeover. Many web services offer to check if your email address or phone number is in a leaked database; HaveIBeenPwned is one of the free services. 

### Searching GitHub Repos

GitHub is a renowned platform that allows developers to host their code through version control. A developer can create multiple repositories and set the privacy setting as well. A common flaw by developers is that the privacy of the repository is set as public, which means anyone can access it. These repositories contain complete source code and, most of the time, include passwords, access tokens, etc. 



# Let's start gathering information.

<img width="300" src="https://user-images.githubusercontent.com/56886006/208966351-d3014112-87a6-483f-b813-e84f3b420c93.png">    
    
## Process:

The first we need to do is find the name of the Registrar for the domain `santagift.shop

To do this we will used who.is and search the URL `santagift.shop`
    
<img width="500" src="https://user-images.githubusercontent.com/56886006/208966413-58d8fc55-3564-42dd-891f-3cd028f13984.png">

This is the results:

<img width="500" src="https://user-images.githubusercontent.com/56886006/208966450-3bd92bd6-b180-48aa-bcfd-1316fb09b8d6.png">

As you can see the Registrar for the domain santagift.shop is `NAMECHEAP INC`

A domain registrar, sometimes called a DNS registrar (short for domain name server), is a business that sells domain names and handles the business of registering them. Domain names are the main address a website uses on the web—they’re the thing that usually starts with `www` and most often ends with `.com`.

Now we had to find the websites github. Going to github.com and searching for the website URL in githubs search bar under `All Repositories`, gave us the correct repo.

<img width="500" src="https://user-images.githubusercontent.com/56886006/208966666-ddea5a82-657d-48eb-964d-c77363f56796.png">

Now that we found the repo, THM asks for the flag in the file containing sensetive information and what is the file containing the name of the passwords?

<img width="500" src="https://user-images.githubusercontent.com/56886006/208966713-2adc62f8-f1a1-46f6-aec5-abe7e2f5b065.png">

Being no stanger to programming I decided that the `config.php` file was my best bet to start my search for any passwords, credentials, etc, as that is usually where they are stored.

Instantly we get our flag.

<img width="500" src="https://user-images.githubusercontent.com/56886006/208966785-e41cf286-e76f-4d0f-82ee-9ec55b72ba42.png">

We find the AQ server that is associated with website on the readme of the websites github.

<img width="500" src="https://user-images.githubusercontent.com/56886006/208966857-ca5747f7-259d-4c68-a7b8-69caee42954f.png">

To find the `DB_PASSWORD` that is being reused between the QA and PROD environments we simply need to go back to the config.php file where all of the passwords and credentials were stored.

<img width="500" src="https://user-images.githubusercontent.com/56886006/208966893-68ce48bb-b031-430a-b12b-57d18124861a.png">
<img width="500" src="https://user-images.githubusercontent.com/56886006/208966951-f0805b2d-157b-41d9-9ea4-4d85738f5dad.png">



h4ppy hunt1ng!    
    
s1l1c0np1r4t3
