
# Brute Force Login Bypass - Local Website Demonstration

**Author:** Shaurya Singh  
**Project Type:** Personal Security Research Project  
**Repository:** https://github.com/sh1nzer/brute-force-login-bypass.git

## Project Overview

This project demonstrates a brute force attack vulnerability on a simulated educational website. The demonstration is designed for cybersecurity learning purposes, showcasing common security weaknesses and their exploitation methods.

## Description - Sample Website Backstory

- **A-Z Education** is a mock educational platform offering courses in React Development, Amazon Web Services, and Cyber Security algorithms.
- The website features a login system where users create accounts to purchase and access video content.
- **Critical Security Flaw:** The platform lacks multi-factor authentication (MFA), including:
  - No One Time Passwords (OTP)
  - No security questions
  - No email verification
  - No rate limiting on login attempts

This absence of security measures makes the system vulnerable to various attack vectors, particularly brute force attacks.

## Attack Methodology: Brute Force Login Bypass

This demonstration involves attempting to gain unauthorized access to the administrator panel using automated credential testing. The attack employs Burp Suite's Intruder tool to systematically test common usernames and passwords.

### Attack Phases:
1. **Username Enumeration:** Identify valid admin username
2. **Password Discovery:** Brute force the corresponding password
3. **Access Achievement:** Successfully log into the admin dashboard

## Prerequisites

- Python 3.x
- Burp Suite (Community or Professional Edition)
- Flask framework

## Setup and Execution Steps

### 1. Environment Setup
```bash
git clone https://github.com/sh1nzer/brute-force-login-bypass.git
cd brute-force-login-bypass
pip install flask
python app.py
```

### 2. Burp Suite Configuration
- Launch Burp Suite
- Configure browser proxy settings
- Access the local website through Burp's browser
- Enable request intercept

### 3. Initial Request Capture
- Navigate to the login panel
- Submit any test credentials
- Capture the POST request in Burp Suite Proxy

### 4. Username Enumeration Attack
- Send captured request to Burp Intruder
- Configure attack type: **Sniper**
- Set payload position on the username parameter
- Load the provided `usernames.txt` wordlist
- Execute the attack and analyze response codes

### 5. Password Brute Force Attack
- Once valid username is identified (different HTTP response code)
- Reconfigure Intruder to target the password parameter
- Load the password wordlist
- Execute the attack to identify valid credentials

### 6. Successful Authentication
- Use discovered credentials to access admin panel
- Document successful unauthorized access

## Key Attack Indicators

- **Response Code Analysis:** Valid credentials typically return different HTTP status codes
- **Response Length Variations:** Successful logins often have different response sizes
- **Response Time Differences:** Authentication success may cause timing variations

## Security Mitigation Strategies

### Primary Defenses:
1. **Strong Password Policies**
   - Minimum 12 characters
   - Complex character requirements
   - Regular password rotation

2. **Account Lockout Mechanisms**
   - Limit failed login attempts (3-5 attempts)
   - Progressive delay increases
   - Temporary account suspension

3. **Multi-Factor Authentication (MFA)**
   - SMS-based OTP
   - Authenticator app integration
   - Hardware security keys

### Additional Security Measures:
4. **IP Address Monitoring and Blocking**
5. **CAPTCHA Implementation**
6. **Unique Administrative URLs**
7. **Web Application Firewall (WAF) Deployment**
8. **Real-time Security Monitoring**
9. **SSH Root Login Restrictions**
10. **Regular Security Audits**

## Educational Purpose Disclaimer

This project is developed solely for educational and authorized security testing purposes. The techniques demonstrated should only be used on systems you own or have explicit permission to test. Unauthorized access to computer systems is illegal and unethical.

## Contributing

This is a personal research project by Shaurya Singh. If you'd like to suggest improvements or report issues, please feel free to open an issue or submit a pull request.


**⚠️ Security Notice:** Always ensure you have proper authorization before conducting any security testing. This demonstration is intended for controlled, educational environments only.
```




