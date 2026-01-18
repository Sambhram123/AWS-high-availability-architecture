# AWS High-Availability Web Architecture

## Project Overview
I designed and deployed a fault-tolerant, highly available web architecture on AWS. The system handles server failures automatically and manages traffic surges without downtime using a custom VPC, Load Balancers, and Auto Scaling.

## Architecture Highlights
* **Cloud Provider:** AWS (Amazon Web Services)
* **Region:** ap-south-1 (Mumbai)
* **Availability Zones:** 2 (ap-south-1a, ap-south-1b)

## Key Services Used
* **VPC:** Custom network with public/private subnet segmentation for security.
* **EC2:** Virtual servers hosting the Apache web application.
* **Auto Scaling Group:** Automatically detects unhealthy instances and launches replacements to ensure 2 servers are always running.
* **Application Load Balancer (ALB):** Distributes incoming traffic across multiple zones.
* **Security Groups:** configured as a "Chained Firewall" where App Servers only accept traffic from the Load Balancer.

## Project Evidence

### 1. Successful Deployment
The application is running on private servers but is accessible via the Load Balancer DNS.
![Website Proof](website-proof.png)

### 2. Health Checks & High Availability
The Target Group confirms that instances across both Availability Zones are healthy and active.
![Health Status](health-check.png)

## Automation Script
The servers are automatically configured using this User Data script during launch:
[View Configuration Script](user-data.sh)

---
*Project created by SAMBHRAM NAIK*
