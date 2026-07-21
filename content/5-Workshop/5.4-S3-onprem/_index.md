---
title : "Access S3 from on-premises"
date : 2024-01-01
weight : 4
chapter : false
pre : " <b> 5.4. </b> "
---

In a Cloud Office system, the Backend Server is deployed in a Private Subnet to limit direct internet access. However, the server still needs to connect to several AWS services to support system operation, such as:

AWS Systems Manager (SSM) for server administration.

Amazon CloudWatch for logging and application monitoring.

AWS Secrets Manager (if used) to store database connection strings and sensitive information.

Without using a VPC Interface Endpoint, these requests would have to go through an Internet Gateway or NAT Gateway. This increases costs and reduces security.

In this practical exercise, we will create a VPC Interface Endpoint so that the Cloud Office Backend Server can access AWS services entirely through the AWS internal network.
