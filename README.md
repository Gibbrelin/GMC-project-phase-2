# HOW TO SET UP ZAP

WHAT IS OSWAP ZAP 

OWASP ZAP (Zed Attack Proxy) is a popular open-source security tool developed and maintained by the Open Web Application Security Project (OWASP). It is used for finding vulnerabilities in web applications and provides features like automated scanners, manual testing tools, and more.

Key Features of OWASP ZAP:


Proxy Server: Acts as an intermediary between your browser and the target web application, allowing you to intercept and inspect traffic.
Automated Scanner: Performs automated vulnerability scans on web applications.

Manual Testing Tools: Includes a suite of tools for manually exploring and testing web applications.

Passive Scanning: Analyzes HTTP requests and responses for potential security issues without altering the traffic.

Active Scanning: Probes the application with various payloads to find vulnerabilities.

Fuzzing: Sends a large number of inputs to the application to discover issues like SQL injection, XSS, and more.

Spidering: Crawls the application to discover all available pages and inputs.

Extensions: ZAP has a marketplace for plugins that extend its functionality.

Typical Use Cases:

Penetration Testing: Security professionals use ZAP to identify and exploit vulnerabilities in web applications.

Development Security: Developers can use ZAP to test their applications during the development process to identify and fix security issues early.

Security Training: ZAP is often used in training environments to teach web application security.

Setting Up OWASP ZAP:

Download and Installation: Download the appropriate version from the official OWASP ZAP website and install it on your system.

Configuration:
Set up your browser to use ZAP as a proxy server. Typically, ZAP runs on localhost:8080.
Install ZAP's root CA certificate in your browser to intercept HTTPS traffic.

# USING ZAP FOR A SECURITY SCAN:
1. open the ZAP application and get familiar with the interface

   ![Screenshot 2024-08-02 102625](https://github.com/user-attachments/assets/d7a6d642-b084-4330-9331-3a46e8016c22)

2. Set the target url to the webpage url, enter the url to attack and click on the attack button

   ![Screenshot 2024-08-02 103241](https://github.com/user-attachments/assets/76f1cab7-9d62-4378-a36a-9bb967f1d512)

3. After clicking one the attack button ZAP starts spidering to discover all pages and endpoints of the targeted web application

 ![Screenshot 2024-08-02 103329](https://github.com/user-attachments/assets/1d23f1d9-d31e-42af-b922-10dd865b2ea0)

4. When the spidering is done ZAP begins active scanning on the web applications to search for vulnerabilities on the web application

  ![Screenshot 2024-08-02 103551](https://github.com/user-attachments/assets/13c25443-b9b7-4681-ac02-35ffc4143edc)

5. After after active scanning is done it brings alert of different vulnerabilties found on the web application

   ![Screenshot 2024-08-02 103645](https://github.com/user-attachments/assets/29e75643-1bd6-4680-bbcf-61a8a8aedfae)

 ALERTS CONDITIONS
Red flag: high/critical vulnerability
Orange flag: medium vulnerability
Yellow Flag: low vulnerablilty
Blue flag: very low vulnerability
   
   





   
