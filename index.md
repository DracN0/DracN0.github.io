# OSCP and Penetration Testing Blog

This blog will be used to include all gathered techniques, methods, and research used for penetration testing on both Hack The Box & OSCP/PWK.

# Enumeration

Enumeration is the absoulute most important yet tedious part of a penetration test. If you feel like you have hit a wall, specifically for HTB/OSCP/PWK, you most likely have not done enough enumeration. Something that helps keep me focused and "mentally organized" is to have the mindset:
"There is a way in. I just need to narrow down where it's at."

Don't worry if enumeration is hard for you, especially at first. The more you do it, the more you'll get used seeing standard services like SSH, FTP, HTTP, etc. & what to use them for. If you want to improve, just get your hands dirty. Experience is the best teacher.



## Where to start

### Note Taking 

Taking organized notes is severely important. I cannot stress it enough that your documentation is both very important to you, and far more important to the client. Develop good note taking habits, as if all of your notes could be handed to your client at any moment. Otherwise, you'll find yourself missing services, directories, steps you took leading up to your initial shell or a cluster of screenshots with sub par explanations of what your screenshot means.

I personally use Microsoft OneNote and highly recommend it. 

#### Other community suggested note taking resources.

* cherrytree (https://www.giuspen.com/cherrytree/)
  * I've read people had issues with cherrytree when it comes to making large files, this steered me away.
* Obsidian - really badass (https://obsidian.md/)
* Evernote - (https://evernote.com/)

### Nmap
Nmap is used to discover hosts and services on a computer network by sending packets and analyzing the responses. Nmap provides a number of features for probing computer networks, including host discovery and service and operating system detection.

My most effective method for Nmap scanning is to do a full scan with verbose output.

```nmap -sV -sC -Pn -p- -vv <host>```
#### What each script does
* -sV Probe open ports to determine service/version info
* -sC equivalent to --script=default 
  * This will run nmap default nse scripts (https://nmap.org/book/man-nse.html)
* -Pn Treat the target as "online"
* -p- will scan all ports
  * To scan individual ports, ssh for example
  ```nmap -sV -sC -Pn -p 22 -vv <host>```
  * You can also specify multiple ports
  ```nmap -sV -sC -Pn -p 22,80,445 -vv <host>```
* -vv will show open port detections in real time so you wont have to wait for the full scan to finish before knowing if a port is open to access.
  
Remember to always check the man pages, or for all Nmap optional flags
```Nmap --help```
  
(page will be updated further soon...)
