---
title : "Access S3 from VPC"
date : 2024-01-01
weight : 3
chapter : false
pre : " <b> 5.3. </b> "
---

1. Introduction to S3 Gateway Endpoint

The Amazon S3 Gateway Endpoint is a type of VPC Endpoint that allows resources within an Amazon VPC to directly access Amazon S3 services via the AWS internal network. Unlike accessing S3 via an Internet Gateway or NAT Gateway, the Gateway Endpoint uses the VPC's Route Table to route traffic to S3, preventing data from passing through the public internet.

2. Cloud Office System Context

In a Cloud Office system, users frequently upload and download various types of documents such as office lease agreements, office images, invoices, and customer verification documents. These documents are stored on Amazon S3 to ensure scalability and data durability.

The system's backend is deployed on Amazon EC2 in a Private Subnet to enhance security. Without configuring an S3 Gateway Endpoint, S3 access requests would have to go through a NAT Gateway or Internet Gateway. This both increases data transmission costs and creates an unnecessary internet connection point.

3. Architecture before and after configuration

Before creating the Gateway Endpoint

EC2 Backend

│

▼
NAT Gateway

│

▼
Internet

│

▼
Amazon S3

After creating the Gateway Endpoint

EC2 Backend

│

▼
Route Table

│

▼
S3 Gateway Endpoint

│

▼
Amazon S3
