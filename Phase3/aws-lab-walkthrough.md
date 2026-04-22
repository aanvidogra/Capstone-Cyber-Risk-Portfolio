AWS Lab Environment Walkthrough
Overview

This section provides a step-by-step walkthrough of the AWS lab environment created for the cyber risk assessment. The purpose of this walkthrough is to document the infrastructure setup and provide visual evidence of the system configuration. Screenshots are included to demonstrate key components of the environment and support later vulnerability and risk analysis.

Step 1: Virtual Private Cloud (VPC) Setup

A Virtual Private Cloud (VPC) was created to simulate the company's internal network. The VPC provides an isolated environment where all resources are deployed.

The VPC uses a private IP address range and acts as the foundation for all networking components.

Step 2: Subnet Configuration

Two subnets were created within the VPC to separate public and private resources.

Public Subnet: Hosts internet-facing systems
Private Subnet: Hosts internal systems

This separation ensures that critical systems, such as the database, are not directly exposed to the internet.

Step 3: Routing and Internet Connectivity

An Internet Gateway was attached to the VPC, and a route table was configured to allow internet access for the public subnet.

The route 0.0.0.0/0 directs external traffic through the Internet Gateway, enabling communication with the public web server.

Step 4: Web Server Deployment

An EC2 instance named CompanyWebServer was deployed in the public subnet. Apache was installed and configured to host a simple company website.

The server is accessible via a public IP address, demonstrating that it is exposed to the internet.

Step 5: Security Group Configuration (SSH Exposure)

The web server is associated with a security group that allows inbound SSH access from any IP address.

This configuration represents a security vulnerability, as it allows potential attackers to attempt unauthorized access to the system.

Step 6: Database Server Deployment

A second EC2 instance named CompanyDatabaseServer was deployed in the private subnet.

The database server does not have a public IP address, indicating that it is not directly accessible from the internet. This demonstrates network segmentation within the environment.

Step 7: S3 Bucket and Data Storage

An Amazon S3 bucket was created to simulate company data storage. A file named customer-data.csv was uploaded to represent sensitive customer information.

The bucket was intentionally configured with public access permissions, allowing anyone with the object URL to access the file. This represents a critical data exposure vulnerability.

Step 8: Network Exposure Verification 

A network scan was performed using nmap to identify open ports on the web server.

The scan shows that ports 22 (SSH) and 80 (HTTP) are open, confirming that the server is accessible from the internet and exposed to potential attacks.

Summary

The AWS lab environment successfully simulates a real-world cloud infrastructure with both secure configurations and intentional vulnerabilities. The screenshots included in this walkthrough provide visual confirmation of the system setup and support the identification of security risks analyzed in later sections of the project.
