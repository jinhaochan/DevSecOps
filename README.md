# DevSecOps
Practical Security Automation and Testing

This README provides an overview of security testing in DevSecOps

TLDR
--

- Automated Testing Frameworks
    - Selenium
- Secure Code Review
    - Insecure Function Calls
        - `exec`
        - Shell execution
    - Insecure Data
        - Private keys
        - Hashes
    - Private Data
        - PII
        - IC Number
        - Email Address
        - Phone Number
- API Testing
    - ZAP
    - Selenium
    - Postman
    - wfuzz
    - radamsa
    - 0d1n
- Infrastructure Testing
    - Network Scanning
        - Namp
    - Component Scanning
        - OWASP Dependency Checking
        - Retire.js
    - Server Hardening Configuration
        - STIGs
        - OpenSCAP
- Web Security Testing
    - ZAP Simple Scan
    - Run ZAP in Proxy mode to inspect HTTP requests/responses
    - Run Selenium through ZAP Proxy
- Android Testing
    - Secure Code Scanning
        - Fireline
    - Privacy and Sensitive Information Scanning
        - Androwarn
    - APK Scanning
        - QARK
    - All-In-One Scanning
        - MobSF

Scope and Challenges of Security Automation
---

Automated security testing does not aim to replace manual security testing, but to address the low hanging fruits so that the penetration testers can focus on more in-depth ones

Resources for security issues:
1. OWASP top 10
2. CWE top 25

Facts:
1. Security Testing does not require highly trained pen testers
2. There are plenty of security automation tools out there to seamlessly integrate with your workflow (Selenium)
3. There are different security testing tools for different scenarios
    - Whitebox: Secure Code Analysis with  `Visual Code Grepper`
    - API Testing: `JMeter`, `FuzzDB`, `OWASP ZAP`
    - Web UI Testing: `Selenium`, `OWASP ZAP`

Integrating Security and Automation
---

### Domains of Security Automation testing

- Code Inspection (Easy)
- Whitebox Unit Testing testing (Easy)
- Acceptance testing (Medium)
- Integration testing (Medium)
- API testing (Medium)
- Blackbox testing (Hard)

### Sample tools for Security Automation

- Selenium (UI)
- JMeter (API)
- Postman (API)
- GrepBugs (Whitebox code scanner)
- ripgrep (Whitebox code scanner)
- Robot Framework (BDD testing `Given ... When ... Then ...`)
- Mockaroo (Test data generator)

### Sample Scenarios for Automated Security Tests

- WebUI Testing
    - Selenium
    - Robot Framework
    - OWASP ZAP

- API Testing
    - JMeter
    - Postman

- Known Vulnerable Components
    - OWASP Dependency Checks
    - OpenVAS

- Networking testing
    - Nmap

- BDD Testing (aid in communicating security scenarios to non-technical team)
    - Robot Framework

- Fuzz Testing
    - FuzzDB
    - Radamsa

- Secure Code Review
    - Visual Code Grep
    - Bandit (Python)

- Secure Configuration
    - OpenSCAP (Scans Linux Configurations)

- SSL Testing (Misconfiguration of SSL)
    - SSLLabs-Scan
    - SSLyze

Secure code Inspection (Whitebox Testing)
---

- Grepping of certain security issues:
    - Weak Encryption Algorithms
    - Insecure Protocols
    - Risky Functions calls (Deseralization, Exec, Shell Execute)

- Tools
    - SWAMP (Software Assurance Marketplace)
    - CRASS (Code Review Audit Script Scanner)
    - VCG (Visual Code Grepper)


Sensitive Information and Privacy Testing
---

Finding sensitive information in:
1. Source code
2. Application
3. Database

Classifications of Sensitive Information
1. PII
    - Credit Card Number
    - IC Number
    - Email Addresses
    - Phone Numbers
    - ...
3. Application/System information
    - Passwords
    - API Keys
    - Private Keys
    - Hashes
    - SQL Statements
    - IP Addresses
    - ...


API Fuzzing and Testing
---

Focus is on Data Injection and Abnormal Payloads

Tools for API Testing

- Sending Inputs
    - FuzzDB
    - Radamsa
    - NaughtyStrings
    - SecList
- Sending Data to the API
    - curl
    - Postman
- Processing Response Data
    - ASTRA
    - ZAP + OpenAPI
    - JMeter
    - Other API testing frameworks


Web Application Security Testing
---

1. ZAP Spider Scan
    - Uncovers all paths in the web application
    - Monitors Requests and Responses for security issues (HTTP headers)
2. ZAP Active Scan
    - Sends malicious inputs to the paths in the application

ZAP + Web Automation using Selenium

Selenium does some web automation, such as logging in, or activating certain functions. These will help guide ZAP in the security scanning


Android Security Testing
---

Approaches:
1. Secure Code Scanning
    - SQL Injection
    - Command Injection
    - SSL Handling
    - WebView XSS
    - Insecure File Access
    - Insecure Communication
3. Sensitive Information Scanning
    - Telephone Identifiers
    - Audio/Video Interception
    - Suspicious Backdoor Connection
    - SMS and Call Abuse
    - Data Leakage
    - Root Behaviors
5. APK Security Scanning
    - Tools: Androwarn
7. Static + Dynmaic Scanning
    - Tools: MobSF


Infrastructure Security
---

Components:
1. Operating Systems
2. Virtualizations
3. Containers
4. Web Services
5. Databases
6. Communications

Guidelines for Infrastructure Security Configuration
- Center for Internet Security
    - Desktop and Browsers
    - Mobile devices
    - Network devices
    - Security Metrics
    - Servers
    - Virtualization
    - Cloud
- Security Technical Implementation Guides (STIGs)
    - Application Security
- OpenSCAP Security Guideline
    - Operating System Security

Scanning Approaches
- nmap VulnScan
    - Scans network vulnerability
- OWASP Dependency Checks
    - Scans local files, libraries for vulnerabilities

Checking HTTPS Security with SSLyze
- Checks for weak cipher suites, insecure renegotiation, Heartbleed attack, invalid certificates and secure/deprecated protocols

Behavior Driven Development
---

Used to improve the communication of the nature of the security testing to all functional teams involved

Security Testing Communication using GWT Scenarios (Given, When, Then)

Robot Framework
- Robot Framework makes it easier to understand the intent of the test using keywords such as `Execute Command` and `Should Not Contain`
- You can integrate security tools such as ZAP with Robot Framework

Selecting Tools for Automation
---

- Is it open source?
- Is it cross platform
- What interfaces are there? (GUI vs headless)
- What is the reporting format?

Testing Frameworks (such as Robot Framework) wraps around the security tools to perform security testing of the application. This includes performing the tests, and generating the reports

Recommended tools:
- ZAP
- Robot Framework
- Selenium (for Web UI automation)
- Nmap (Network scanner)
- Postman (Sending HTTP requests)
- sslScan (Scans vulnerable SSL)
- wfuzz (Fuzzing HTTP Requests)
- Retire.js (Scan vulnerable Javascript libraries)

Case Study for Web Security
---

Automated Testing of Web Application
- ZAP
- Selenium
- FuzzDB

Steps
- ZAP simple scan for injection vulnerabilities
- Automated Web UI steps with Selenium (such as user login)
- Run ZAP in Proxy mode to monitor the HTTP requests/reponses
- Run Fuzzing for XSS and SQLi

Case Study for API Testing
---

Data Sources:
- FuzzDB
- Naughty Strings
- SecList
- Radamsa

Fuzzing Tools:
- wfuzz
- 0d1n

Testing Frameworks
- Selenium
- Robot Framework

Case Study for Infrastructure Testing
---

- Scan for JavasScript Vulnerabilities
    - Retire.js
- Scan for Vulnerable Dependencies
    - OWASP Dependency Check
- Scan for Secure Communication
    - SSLScan
- Scan for Secure Networking
    - Nmap



