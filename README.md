# CEH MASTER PREP MATERIAL.

## IMPORTANT:
I have decided to document my journey in the preparation to the exam and most importantly,
for life. As much as I would be over the moon after acing the exam, the excitement always ends in
the same day. To me, the most important is, "I study for life...!"

## Exam Details
- Exam Title: Certified Ethical Hacker - Master (Practical Exam)
- Number of Challenges -> 20
- Duration -> 6 hours
- Availability -> Aspen-iLabs
- Test Format -> iLabs Cyber Range
_ Passing Score(14 Questions) -> 70% (I am going for 100%)

## Requisites
- Should have already done test with iLabs
- One Kali linux(No update) & Window Server
- Five machines to compromise on isolated networks
- Open Books(Google, confirm from book)
- No consultation during the Exam

## Topics Examined
1. Vulnerability Analysis: for the following Networks;  Organizations, Communication Infrastructure, End Systems, etc
2. System Hacking & Steganography
3. Reconnaisance; Network scanning to identify vulnerability
4. OS Banner Grabbing, Service & User Enumeration
5. Cryptography Attacks
6. SQL Injection attacks
7. Packet Sniffing

 ## Tools & Short Notes Per Topic
1. Vulnerability Analysis
Notes: 
	- Is the process of breaking the system into bits in order to identify and classify the security holes.

Tools: 
  - [*] - Nmap, ncat, ndiff, nping
  - [] - ftp
  - [] - 
  - [] - COPS
  - [] - Tiger
  
  Windows Tools
  - Wireshirk --> Used to monitor network traffic, can be used to tell whether we have a DDOS attack or not
  - Hashcalc --> Used to calculate for the hash value of a file or text
  - Veracrypt --> Used to encrypt and decrypt storage volumes/files
  - BCText Encoder -> Encodes & decodes given text as long as a password is provided
  - Cryptool --> Used to decode a hex file
  - Snow --> Used to extract hidden messages in files(password protected)
  - Openstego --> Used to extract hidden information in audio, video, images and text file
  
  Linux Tools
  - Netdiscover --> Identify the devices connected to your network
  - NMAP --> scan network for vulnerability & open ports
  - Hydra --> Online password cracker.
  - John The Ripper --> Brute force password cracker, can crack linux login passwd, zipped files etc. 
  - wpscan --> Wordpress sanner, scans the wordpress site for vulnerabilities.
  - sqlmap --> traces/enumerates existing databases and dumps data. 
  - ADB --> used to manage adroid, install uninstall apps, list running services, traverse the file sys, clear cache etc. on the shell

Bonus Tools

Reco
- Sherlock --> for social media accounts


Exam Questions
1. How Many machines are active ? (Use netdiscover)
2. Which Machine has FTP Server open ? (nmap)
3. Find 2 secret files using FTP? (Brute force FTP usernames)
4. Find out phone number of web application user? (sqlmap)
5. Brute force Wordpress website user's password. (wpscan)
6. Decode .hex file (cryptool)
7. Which machine started DOS attack? DDOS attack happened on which IP? Find out HTTP credentials from PCAP file? (wireshark)
8. Decode the given text using given secret? (BCTextEncoder)
9. Calculate SHA1 hash of a text? (Hashcalc)
10. Decrypt the hidden volume & find the secret file? (veracrypt)
11. Crack the given hash? (hashes.com)
12. Find secret hidden in the image/file ? (Openstego/Snow)
13. Find a secret file in ADROID ? (adb)
14. Send data to another machine(firewall blocked) ? (Covert TCP)

NB:-
- A summary documentation of each tool is in in the markdown file named with the respective name of each tool
- The documentation will be updated from time to time.
