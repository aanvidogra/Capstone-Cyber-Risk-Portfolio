Cybersecurity Vulnerability Identification
Overview

The AWS lab environment was analyzed to identify cybersecurity vulnerabilities that could impact the simulated company's operations. These vulnerabilities are based on the infrastructure deployed in Phase 3 and are mapped to business assets identified in Phase 1. Each vulnerability represents a potential risk to the confidentiality, integrity, or availability of company systems and data.

Vulnerability 1: Publicly Accessible S3 Bucket

Asset: Customer Data (S3 Storage)
Threat: Unauthorized data access
Vulnerability: Public read access enabled on S3 bucket

The S3 bucket used to store company data was configured with a public access policy, allowing any user on the internet to access the file customer-data.csv. This represents a critical misconfiguration because it exposes sensitive customer information without authentication or authorization.

Business Impact:

Exposure of customer data
Loss of customer trust
Potential legal and regulatory consequences
Financial loss due to data breach response
Vulnerability 2: SSH Access Open to the Internet

Asset: Company Web Server (EC2 Instance)
Threat: Unauthorized system access
Vulnerability: SSH port (22) open to all IP addresses (0.0.0.0/0)

The web server security group allows SSH access from any IP address, making it vulnerable to brute-force attacks and unauthorized login attempts. Attackers can continuously scan and attempt to gain access to the server.

Business Impact:

Unauthorized access to server
System compromise
Deployment of malware or backdoors
Service disruption
Vulnerability 3: Publicly Accessible Web Server

Asset: Company Website (Web Server)
Threat: External attacks (e.g., scanning, exploitation)
Vulnerability: HTTP service exposed to the internet

The web server is publicly accessible, which is required for business functionality, but also introduces risk. The server can be scanned for vulnerabilities, targeted with exploits, or used as an entry point into the network.

Business Impact:

Website defacement
Downtime affecting customers
Potential pivot point for further attacks
Reputation damage
Vulnerability 4: Lack of Encryption on Data Storage

Asset: Database and Stored Data
Threat: Data interception or unauthorized access
Vulnerability: No encryption configured for stored data

The database server and S3 storage do not enforce encryption for sensitive data. If accessed by an attacker, data could be read in plain text, increasing the severity of a breach.

Business Impact:

Exposure of sensitive data
Non-compliance with security standards
Increased breach impact
Loss of confidentiality
Vulnerability 5: Internal Database Server Trust Relationship

Asset: Company Database Server
Threat: Lateral movement within the network
Vulnerability: Database accessible from web server without additional controls

Although the database server is not publicly accessible, it allows connections from the web server. If the web server is compromised, the attacker could move laterally to the database and access sensitive information.

Business Impact:

Full data compromise
Escalation of attack impact
Loss of critical business data
Increased recovery costs
Summary

The vulnerabilities identified in this environment demonstrate common cloud security risks, including misconfigured storage permissions, overly permissive network access, and insufficient data protection. These issues highlight the importance of proper security controls in protecting business assets and maintaining operational integrity.
