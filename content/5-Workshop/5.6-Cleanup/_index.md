---
title : "Clean up"
date : 2024-01-01
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---
1. Deleting Objects in an Amazon S3 Bucket

Access the Amazon S3 Console.

Open the Bucket created in the workshop.

Select all uploaded files (e.g., office-contract-demo.pdf) and click Delete.

Note: Amazon S3 does not allow deleting a Bucket if it still contains data.

2. Deleting an Amazon S3 Bucket

After the Bucket is empty:

Return to the Buckets list.

Select the Cloud Office Bucket.

Select Delete.

Enter the Bucket name to confirm.

Click Delete bucket.

3. Deleting an S3 Gateway Endpoint

Open the Amazon VPC Console.

Select Endpoints.

Select the created Endpoint.

Click Delete endpoint and confirm the action.

After deletion, the Route Table will automatically remove the route created for the Gateway Endpoint.

4. Check remaining resources

Review the following services to ensure no resources are being used from the workshop:

Amazon EC2
Amazon VPC Endpoints
Amazon S3 Buckets
Security Groups (if created separately)
CloudFormation Stack (if used for infrastructure deployment)
