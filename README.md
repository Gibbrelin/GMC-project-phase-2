# DISCOVERING THE WEBPAGE URL
# Tools Needed:

VMWARE

KALI LINUX

WEBPAGE VIRTUAL MACHINE

# Configuring your webpage virtual machine

Step 1.download a webpage hosting page virtual machine from https://www.vulnhub.com/entry/drunk-admin-web-hacking-challenge-1,14/ for vmware 

Step 2.install the virtual machine

Step 3. in the vmware application go to the settings then network adapter

Step 4. change it to custom (vmnet1) for both your kali linux and the web hosting page virtual machine

# Discovering the webpage url

Step 1. log in to your kali VM

step 2. on the terminal input IFCONFIG to know the host ip address

   ![Screenshot 2024-08-02 101507](https://github.com/user-attachments/assets/8a4bc3f6-957e-4af6-8b9a-e04343b4efb1)

   pay attention to the ipv4 address and the mac address (which in my case is 192.168.65.128 and 00:0c:09:25:9a:5c)

Step 3. then we run netdiscover on the ip address to know the ip addresses running on the host using SUDO NETDISCOVER -R ip address ( sudo netdiscover -r 192.168.65.0/24)
   ![Screenshot 2024-08-01 210334](https://github.com/user-attachments/assets/00aec24f-0ea6-4b46-a8fb-500e347fb01d)

Checking the discovered host one of the discovered ip address has the same mac address as the normal ip address which is most likely our webpage ip address

Step 4. to validate if its the ip address of the webpage we use nmap to scan the ipaddress using the command nmap -p 8880 192.168.65.129
 ![Screenshot 2024-08-01 210437](https://github.com/user-attachments/assets/c886d839-0e2b-4e42-aabf-37306a3d4ada)
  The nmap scan validates that the ip address over that port is open

step 5. we go to our web browser and input our ip address url
![Screenshot 2024-08-02 102952](https://github.com/user-attachments/assets/91743063-98e6-4793-9fc1-9723b7f782e4)

and we have our webpage!

# HOW TO SET UP ZAP

WHAT IS OSWAP ZAP 

OWASP ZAP (Zed Attack Proxy) is a popular open-source security tool developed and maintained by the Open Web Application Security Project (OWASP). It is used for finding vulnerabilities in web applications and provides features like automated scanners, manual testing tools, and more.

# Key Features of OWASP ZAP:


Proxy Server: Acts as an intermediary between your browser and the target web application, allowing you to intercept and inspect traffic.
Automated Scanner: Performs automated vulnerability scans on web applications.

Manual Testing Tools: Includes a suite of tools for manually exploring and testing web applications.

Passive Scanning: Analyzes HTTP requests and responses for potential security issues without altering the traffic.

Active Scanning: Probes the application with various payloads to find vulnerabilities.

Fuzzing: Sends a large number of inputs to the application to discover issues like SQL injection, XSS, and more.

Spidering: Crawls the application to discover all available pages and inputs.

Extensions: ZAP has a marketplace for plugins that extend its functionality.

# Typical Use Cases:

Penetration Testing: Security professionals use ZAP to identify and exploit vulnerabilities in web applications.

Development Security: Developers can use ZAP to test their applications during the development process to identify and fix security issues early.

Security Training: ZAP is often used in training environments to teach web application security.

# Setting Up OWASP ZAP:

Step 1. Download and Installation: Download the appropriate version from the official OWASP ZAP website and install it on your system.

Step 2. Configuration:
 . Set up your browser to use ZAP as a proxy server. Typically, ZAP runs on localhost:8080.
. Install ZAP's root CA certificate in your browser to intercept HTTPS traffic.

# USING ZAP FOR A SECURITY SCAN:

Step 1. open the ZAP application and get familiar with the interface

   ![Screenshot 2024-08-02 102625](https://github.com/user-attachments/assets/d7a6d642-b084-4330-9331-3a46e8016c22)

Step 2. Set the target url to the webpage url, enter the url to attack and click on the attack button

   ![Screenshot 2024-08-02 103241](https://github.com/user-attachments/assets/76f1cab7-9d62-4378-a36a-9bb967f1d512)

Step 3. After clicking one the attack button ZAP starts spidering to discover all pages and endpoints of the targeted web application

 ![Screenshot 2024-08-02 103329](https://github.com/user-attachments/assets/1d23f1d9-d31e-42af-b922-10dd865b2ea0)

Step 4. When the spidering is done ZAP begins active scanning on the web applications to search for vulnerabilities on the web application

  ![Screenshot 2024-08-02 103551](https://github.com/user-attachments/assets/13c25443-b9b7-4681-ac02-35ffc4143edc)

Step 5. After after active scanning is done it brings alert of different vulnerabilties found on the web application

   ![Screenshot 2024-08-02 103645](https://github.com/user-attachments/assets/29e75643-1bd6-4680-bbcf-61a8a8aedfae)

# Alearts Conditions

. Red flag: high/critical vulnerability

. Orange flag: medium vulnerability

. Yellow Flag: low vulnerablilty

. Blue flag: very low vulnerability

# Key Findings

No highly severe vulnerabilities were found

Several medium vulnerabilities like cross site scripting and session hijacking was found

![Screenshot 2024-08-02 120842](https://github.com/user-attachments/assets/8e300092-b633-43f6-a32a-c56cda7e24d7)

# Next Steps

. Investigate the vulnerabilities and fix them

. re-scan the web application to check if the vulnerabilties has been fixed

. continue monitoring the web applications by making periodic scannings particularly after making updates and changes





   
