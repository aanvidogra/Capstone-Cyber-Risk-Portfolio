AWS Lab Architecture Design
Overview

The AWS lab environment was designed to simulate the cloud infrastructure of a small company operating in Amazon Web Services (AWS). The goal of this architecture is to create a realistic environment that can be analyzed for cybersecurity risks and vulnerabilities. The environment includes networking components, compute resources, and storage services that reflect common enterprise cloud deployments.

The simulated company hosts a public-facing website, maintains an internal database server, and stores data in an Amazon S3 bucket. The infrastructure is intentionally configured with certain weak security settings to represent real-world vulnerabilities that organizations often face.

Virtual Private Cloud (VPC)

A Virtual Private Cloud (VPC) named CyberRiskLab-VPC was created to provide an isolated network for the company’s infrastructure. The VPC uses the CIDR block:

10.0.0.0/16

This network allows multiple subnets and systems to operate within a controlled environment.

Subnets

Two subnets were created within the VPC to separate public and private resources.

Public Subnet

CIDR: 10.0.1.0/24
Hosts the CompanyWebServer
Connected to the internet via an Internet Gateway

This subnet allows external users to access the company website.

Private Subnet

CIDR: 10.0.2.0/24
Hosts the CompanyDatabaseServer
No direct internet access

This subnet is used to protect sensitive internal systems.

Internet Gateway and Routing

An Internet Gateway was attached to the VPC to allow communication between the public subnet and the internet. A route table was configured with the following route:

0.0.0.0/0 → Internet Gateway

This enables public access to the web server while keeping the private subnet isolated.

EC2 Instances

Two EC2 instances were deployed to simulate company servers.

CompanyWebServer

Located in the public subnet
Assigned a public IP address
Hosts a website using Apache
Accessible from the internet

This server represents the company’s public-facing web application.

CompanyDatabaseServer

Located in the private subnet
No public IP address
Not directly accessible from the internet

This server represents an internal database system.

Security Groups

Security groups were used to control network access.

WebServer-SG

Allows HTTP (port 80) from anywhere
Allows SSH (port 22) from anywhere

This configuration intentionally introduces security risk for analysis.

Database-SG

Allows MySQL (port 3306) only from WebServer-SG

This ensures that only the web server can communicate with the database.

Amazon S3 Storage

An Amazon S3 bucket was created to simulate company data storage. A file named customer-data.csv was uploaded to represent sensitive customer information.

The bucket was intentionally configured with public access permissions, allowing anyone on the internet to access the file. This represents a common cloud misconfiguration that can lead to data breaches.

Architecture Summary

The AWS lab architecture includes a virtual network, segmented subnets, compute resources, and cloud storage. This environment reflects a simplified enterprise cloud infrastructure. It will be used to identify vulnerabilities, analyze cyber risks, and propose mitigation strategies in later phases of the project.
