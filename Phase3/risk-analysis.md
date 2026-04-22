Cyber Risk Analysis
Overview

The vulnerabilities identified in the AWS lab environment were analyzed to determine their risk level based on likelihood and business impact. This analysis aligns with the risk assessment framework established in Phase 1, using a qualitative approach to classify risks as Low, Medium, High, or Critical.

Each risk is evaluated based on:

Likelihood: Probability of the vulnerability being exploited
Impact: Potential damage to the organization if exploited
Risk 1: Public S3 Bucket (Customer Data Exposure)

Asset: Customer Data (S3 Storage)
Threat: Unauthorized access
Likelihood: High
Impact: High
Risk Level: Critical

The S3 bucket is publicly accessible and contains sensitive customer data. Since the data can be accessed by anyone with the object URL, the likelihood of exploitation is extremely high. The impact is also high due to potential legal consequences, financial loss, and reputational damage.

Risk 2: SSH Open to the Internet

Asset: Company Web Server
Threat: Brute-force attack / unauthorized access
Likelihood: High
Impact: High
Risk Level: High

The web server allows SSH access from any IP address, making it a target for automated scanning and brute-force login attempts. While key-based authentication reduces immediate risk, the exposure significantly increases the attack surface.

Risk 3: Public Web Server Exposure

Asset: Company Website
Threat: External exploitation
Likelihood: Medium
Impact: High
Risk Level: High

The web server must be publicly accessible for business functionality, but this exposes it to scanning, vulnerabilities, and potential exploitation. If compromised, it can affect both availability and security of the system.

Risk 4: Lack of Data Encryption

Asset: Database and Stored Data
Threat: Data exposure during compromise
Likelihood: Medium
Impact: High
Risk Level: High

Sensitive data is not encrypted at rest, increasing the severity of any breach. If attackers gain access to storage or the database, the data can be read directly without additional barriers.

Risk 5: Database Access via Web Server (Lateral Movement)

Asset: Company Database Server
Threat: Internal attack propagation
Likelihood: Medium
Impact: High
Risk Level: High

The database server is protected from direct internet access, but it is accessible from the web server. If the web server is compromised, attackers can pivot to the database and gain access to sensitive data.

Risk Summary

The majority of identified risks fall within the High to Critical range, indicating significant security weaknesses in the system. The most severe risk is the publicly accessible S3 bucket, which directly exposes sensitive customer data.

This analysis highlights the importance of implementing proper access controls, encryption, and network segmentation to reduce risk and protect business assets.
