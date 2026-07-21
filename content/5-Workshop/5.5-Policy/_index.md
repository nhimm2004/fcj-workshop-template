---
title : "VPC Endpoint Policies"
date : 2024-01-01
weight : 5
chapter : false
pre : " <b> 5.5. </b> "
---

Practice Content
Open S3 Gateway Endpoint.
Edit Endpoint Policy.
Apply access restriction policy.
Check the results.

Configure Endpoint Policy

Open Amazon VPC → Endpoints.

Select Endpoint:

cloud-office-s3-endpoint

Select the Policy tab.

Change from Full Access to Custom.

Use the following Policy (replace cloud-office-documents with your Bucket name):
{ 
"Version": "2012-10-17", 
"Statement": [ 
{ 
"Sid": "AllowCloudOfficeBucketOnly", 
"Effect": "Allow", 
"Principal": "*", 
"Action": [ 
"s3:GetObject", 
"s3:PutObject", 
"s3:DeleteObject", 
"s3:ListBucket" 
], 
"Resource": [ 
"arn:aws:s3:::cloud-office-documents", 
"arn:aws:s3:::cloud-office-documents/*" 
] 
} 
]
}


Check

Connect to Backend Server using AWS Session Manager.

Try uploading a file to a Cloud Office Bucket:

aws s3 cp office-contract-demo.pdf s3://cloud-office-documents

The command will execute successfully if the Bucket is in the Policy.

Next, try uploading a file to another Bucket:

aws s3 cp office-contract-demo.pdf s3://another-bucket
The AWS CLI will return an "Access Denied" message, indicating that the Endpoint Policy is working correctly and only allows access to the Cloud Office Bucket.
