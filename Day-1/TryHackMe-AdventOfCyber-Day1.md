<img width="600" src="https://user-images.githubusercontent.com/56886006/207661596-f8ed4e39-93e9-4b24-ba68-0d2fade203e0.png">

---

Follow me on twitter to stay updated! [Twitter @s1l1c0np1r4t3x](https://twitter.com/s1l1c0np1r4t3x)

Or get all my links here: [Linktree @s1l1c0np1r4t3](https://linktr.ee/s1l1c0np1r4t3)

---

<img width="500" src="https://user-images.githubusercontent.com/56886006/207661686-f2dc751d-84ef-4a30-9e71-e4398cd45be8.png">

# Day 1

Link to CTF: https://tryhackme.com/christmas

## Description/Debrief

<img width="500" src="https://user-images.githubusercontent.com/56886006/207663052-1f6ecc3d-4068-4374-b440-91271fd06eef.png">

### Best Festival Company Compromised

Someone is trying to stop Christmas this year and stop Santa from delivering gifts to children who were nice this year. The Best Festival Company’s website has been defaced, and children worldwide cannot send in their gift requests. There’s much work to be done to investigate the attack and test other systems! The attackers have left a puzzle for the Elves to solve and learn who their adversaries are. McSkidy looked at the puzzle and recognised some of the pieces as the phases of the Unified Kill Chain, a security framework used to understand attackers. She has reached out to you to assist them in recovering their website, identifying their attacker, and helping save Christmas.

---


# The Process

## Objectives

To go over and learn the various cyber security frameworks.

### Santa's website has been defaced!

<img width="500" src="https://user-images.githubusercontent.com/56886006/207662055-401a6e04-da1d-4e07-909e-e6c84757f688.png">

## Unified Kill Chain

### CYCLE 1: In

The main focus of this series of phases is for an attacker to gain access to a system or networked environment. Typically, cyber-attacks are initiated by an external attacker. The critical steps they would follow are: 

<img width="500" src="https://user-images.githubusercontent.com/56886006/207662117-b4495053-902b-49a5-b15a-f0990eb25648.png">

***Reconnaissance***: The attacker performs research on the target using publicly available information.

***Weaponisation***: Setting up the needed infrastructure to host the command and control centre (C2) is crucial in executing attacks.

***Delivery***: Payloads are malicious instruments delivered to the target through numerous means, such as email phishing and supply chain attacks.

***Social Engineering***: The attacker will trick their target into performing untrusted and unsafe action against the payload they just delivered, often making their message appear to come from a trusted in-house source.

***Exploitation***: If the attacker finds an existing vulnerability, a software or hardware weakness, in the network assets, they may use this to trigger their payload.

***Persistence***: The attacker will leave behind a fallback presence on the network or asset to make sure they have a point of access to their target.

***Defence Evasion***: The attacker must remain anonymous throughout their exploits by disabling and avoiding any security defence mechanisms enabled, including deleting evidence of their presence.

***Command & Control***: Remember the infrastructure that the attacker prepared? A communication channel between the compromised system and the attacker’s infrastructure is established across the internet.

### Puzzle together:

<img width="500" src="https://user-images.githubusercontent.com/56886006/207662185-84dd788c-e684-4a91-8f7e-1c1a94ee0fa1.png">

### CYCLE 2: Through

Under this phase, attackers will be interested in gaining more access and privileges to assets within the network.

The attacker may repeat this phase until the desired access is obtained.

<img width="500" src="https://user-images.githubusercontent.com/56886006/207662230-deecdd3d-f67f-421e-b432-b17f1fb52e59.png">

***Pivoting***: Remember the system that the attacker may use for persistence? This system will become the attack launchpad for other systems in the network.

***Discovery***: The attacker will seek to gather as much information about the compromised system, such as available users and data. Alternatively, they may remotely discover vulnerabilities and assets within the network. This opens the way for the next phase.

***Privilege Escalation***: Restricted access prevents the attacker from executing their mission. Therefore, they will seek higher privileges on the compromised systems by exploiting identified vulnerabilities or misconfigurations.

***Execution***: With elevated privileges, malicious code may be downloaded and executed to extract sensitive information or cause further havoc on the system.

***Credential Access***: Part of the extracted sensitive information would include login credentials stored in the hard disk or memory. This provides the attacker with more firepower for their attacks.

***Lateral Movement***: Using the extracted credentials, the attacker may move around different systems or data storages within the network, for example, within a single department.

### Puzzle together:

<img width="500" src="https://user-images.githubusercontent.com/56886006/207662303-15913fca-dd87-411a-b84f-953a8a2ae1d0.png">

### Cycle 3: Out

The Confidentiality, Integrity and Availability (CIA) of assets or services are compromised during this phase. Money, fame or sabotage will drive attackers to undertake their reasons for executing their attacks, cause as much damage as possible and disappear without being detected.

<img width="500" src="https://user-images.githubusercontent.com/56886006/207662408-3e243e53-95f2-4aea-af5a-f3937d9aec24.png">

***Collection***: After finding the jackpot of data and information, the attacker will seek to aggregate all they need. By doing so, the assets’ confidentiality would be compromised entirely, especially when dealing with trade secrets and financial or personally identifiable information (PII) that is to be secured.

***Exfiltration***: The attacker must get his loot out of the network. Various techniques may be used to ensure they have achieved their objectives without triggering suspicion.

***Impact***: When compromising the availability or integrity of an asset or information, the attacker will use all the acquired privileges to manipulate, interrupt and sabotage. Imagine the reputation, financial and social damage an organisation would have to recover from.

***Objectives***: Attackers may have other goals to achieve that may affect the social or technical landscape that their targets operate within. Defining and understanding these objectives tends to help security teams familiarise themselves with adversarial attack tools and conduct risk assessments to defend their assets.

### Puzzle together:

<img width="500" src="https://user-images.githubusercontent.com/56886006/207662473-955dd174-dc0e-4881-9f74-ca370f34935b.png">

And we got the flag!

<img width="500" src="https://user-images.githubusercontent.com/56886006/207662536-9657867a-767a-460b-8ba6-c37589d95e67.png">

<img width="500" src="https://user-images.githubusercontent.com/56886006/207662806-03d6cd4d-3367-4bf5-8db3-ba8e2fbcb604.png">

## Saving The Best Festival Company

Having gone through the UKC with Santa’s security team, it is evident that better defensive strategies must be implemented to raise resilience against attacks.

Your task is to help the Elves solve a puzzle left for them to identify who is trying to stop Christmas. Click the View Site button at the top of the task to launch the static site in split view. You may have to open the static site on a new window and zoom in for a clearer view of the puzzle pieces.

<img width="500" src="https://user-images.githubusercontent.com/56886006/207662853-180833e9-dc33-4006-b7d1-569acb6445c4.png">



h4ppy hunt1ng!    
    
s1l1c0np1r4t3

