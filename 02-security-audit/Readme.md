# Security Audit — Botium Toys

## Overview
This project is about a security audit of a fictional company called Botium Toys. It's part of the Google Cybersecurity Certificate.

## Scenario
Botium Toys is a small toy company that sells toys online. They are growing and want to make sure their online presence is secure.

## What I did
I was responsible for a comprehensive security audit of Botium Toys, a fictional small toy company experiencing rapid growth. My role involved assessing existing security controls, evaluating compliance with relevant industry standards, and identifying critical vulnerabilities that could expose the company and its customers to security risks.

## Frameworks & concepts applied
I applied the NIST Cybersecurity Framework (CSF), focusing on the Identify function to map existing controls to security requirements, assess current implementations, and applied concepts like control types and the CIA triad to evaluate risks.

## Key findings
The key findings from my audit revealed several critical security gaps at Botium Toys:

1. Lack of Least Privilege: All employees had unrestricted access to all data, including sensitive customer information and payment card details. This violates the principle of least privilege and increases the risk of insider threats or accidental exposure.

2. No Encryption for Sensitive Data: Customer payment card information was stored without encryption, leaving it vulnerable to theft or interception. This is a major compliance failure and puts customers at significant risk.

3. Absence of Backup and Disaster Recovery: The company had no established backup or disaster recovery plan. In the event of a system failure, cyberattack, or natural disaster, all business data could be permanently lost, potentially leading to business collapse.

4. No Intrusion Detection System: Botium Toys lacked an intrusion detection system (IDS) to monitor for malicious activity or unauthorized access attempts. This means the company would be unaware of security breaches until significant damage had already occurred.

These findings indicate that Botium Toys has critical vulnerabilities across several security domains, exposing the company and its customers to substantial risks.

## Recommendations

1. **Implement Least Privilege & Access Controls** 
Restrict employee access so each role can only reach the data it needs. This reduces insider risk and limits the blast radius of a potential breach.

2. **Enforce Encryption** 
Protect customer payment card data both in storage and in transit to ensure confidentiality and maintain compliance with standards such as PCI DSS.

3. **Establish Backups & a Disaster Recovery Plan** 
Regularly back up critical business data and document a clear recovery process to ensure business continuity after an incident or system failure.

4. **Enable Multi-Factor Authentication (MFA)** 
Add a second layer of verification to reduce account takeovers caused by stolen or compromised passwords.

5. **Deploy an Intrusion Detection System (IDS)** 
Monitor network traffic for suspicious or malicious activity that a firewall alone may not catch, enabling faster detection and response to threats.
