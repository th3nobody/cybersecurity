# Task 1: Scan Your Local Network for Open Ports

## Objective:
- Learn to discover open ports on devices in your local network to understand
network exposure

## Tools:
- ip
- Nmap

## Task Solution
### 1. Installing Nmap [Download Nmap suitable for your system](https://nmap.org/download.html).
- In my case (kali linux) i used command `sudo apt install nmap`.
  
 ![img not found](assets/nmap-install.png)

 ### 2. finding Local ip range 
 - command `ip a`

![img not found](assets/ip-scan.png)

Result 
- my device ip: 192.168.1.3
- local IP range:192.168.1.0/24

### 3.  Performing TCP SYN scan using nmap
- command used :`nmap -sS 192.168.1.0/24 -oX network_scan.xml`
  
   here -oX is used to save the output file in xml formal. which can be used in other tools but in my case I have converted that xml into html file
  with the help of xsltproc tool
  
   [guide to comvert xml into html](https://nmap.org/book/output-formats-output-to-html.html),
  
  [other possible output formats in nmap](https://nmap.org/book/output.html)

  ![img not found](assets/nmap-scan.png)

  [Nmap output in html](https://th3nobody.github.io/cybersecurity/task-1/assets/nmap-scan.html).


  

