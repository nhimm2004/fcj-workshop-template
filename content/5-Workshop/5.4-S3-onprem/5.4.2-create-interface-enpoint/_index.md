---
title : "Create an S3 Interface endpoint"
date : 2024-01-01
weight : 2
chapter : false
pre : " <b> 5.4.2 </b> "
---

Objective

In this section, we will create an Interface Endpoint for the AWS services that Cloud Office uses.

Execution

Open Amazon VPC

Select

Endpoints

Select

Create endpoint

Name

Name

cloud-office-ssm-endpoint
Service Category

Select

AWS services
Services

Find

Systems Manager

or

ssm

Select the service

com.amazonaws.<region>.ssm

Interface

VPC

Select

CloudOffice-VPC
Subnets

Select the Private Subnet containing the Backend Server.

Select the Security Group of the Interface Endpoint.

The Security Group needs to allow HTTPS (443) from the Backend Server.

Private DNS

Check

Enable DNS name

This allows the Backend Server to access the AWS service using the default domain name without changing the application.

Press

Create endpoint
