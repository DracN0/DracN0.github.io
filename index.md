# My OSCP and Penetration Testing Blog

This blog will be used to include all gathered techniques, methods, and research used for penetration testing on both Hack The Box & OSCP/PWK.

# Enumeration

Enumeration is the absoulute most important part yet tedious part of a penetration test. If you feel like you have hit a wall, specifically for HTB/OSCP/PWK, you most likely have not done enough enumeration. Something that helps keep me focused and "mentally organized" is to have the mindset:
"There IS a way in. I just need to narrow down where it's at."

Don't worry if enumeration is hard for you, especially at first. The more you do it, the more you'll get used seeing standard services like SSH, FTP, HTTP, etc. & what to use them for. If you want to improve, just get your hands dirty. Experience is the best teacher.



## Where to start

### Nmap
Nmap is used to discover hosts and services on a computer network by sending packets and analyzing the responses. Nmap provides a number of features for probing computer networks, including host discovery and service and operating system detection.

My most effective method for Nmap scanning is to do a full scan with verbose output.

```Nmap -sV -sC -Pn -p- -vv <host>```
#### What each script does
* -sV: Probe open ports to determine service/version info
* -sC: equivalent to --script=default 
  * - This will run nmap default nse scripts (https://nmap.org/book/man-nse.html)
* -Pn: Treat the target as "online"

(page will be updated further soon...)
