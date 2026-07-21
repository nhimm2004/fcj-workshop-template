---
title : "VPC Endpoint Policies"
date : 2024-01-01
weight : 5
chapter : false
pre : " <b> 5.5 </b> "
---

Nội dung thực hành
Mở S3 Gateway Endpoint.
Chỉnh sửa Endpoint Policy.
Áp dụng chính sách giới hạn truy cập.
Kiểm tra kết quả.

Cấu hình Endpoint Policy

Mở Amazon VPC → Endpoints.

Chọn Endpoint:

cloud-office-s3-endpoint

Chọn tab Policy.

Thay đổi từ Full Access sang Custom.

Sử dụng Policy sau (thay cloud-office-documents bằng tên Bucket của bạn):
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


Kiểm tra

Kết nối đến Backend Server bằng AWS Session Manager.

Thử tải một tệp lên Bucket của Cloud Office:

aws s3 cp office-contract-demo.pdf s3://cloud-office-documents

Lệnh sẽ thực hiện thành công nếu Bucket nằm trong Policy.

Tiếp theo, thử tải tệp lên một Bucket khác:

aws s3 cp office-contract-demo.pdf s3://another-bucket

AWS CLI sẽ trả về thông báo Access Denied, cho thấy Endpoint Policy đã hoạt động đúng và chỉ cho phép truy cập Bucket của Cloud Office.
