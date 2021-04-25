# DevSecOps
Practical Security Automation and Testing

This README provides an overview of security testing in DevSecOps

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



