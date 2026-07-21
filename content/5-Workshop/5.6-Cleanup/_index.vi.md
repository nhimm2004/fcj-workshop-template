---
title : "Dọn dẹp tài nguyên"
date : 2024-01-01
weight : 6
chapter : false
pre : " <b> 5.6. </b> "
---

 1. Xóa các đối tượng trong Amazon S3 Bucket

Truy cập Amazon S3 Console.

Mở Bucket đã tạo trong workshop

Chọn toàn bộ các tệp đã tải lên (ví dụ: office-contract-demo.pdf) và nhấn Delete.

Lưu ý: Amazon S3 không cho phép xóa Bucket khi bên trong vẫn còn dữ liệu.

 2. Xóa Amazon S3 Bucket

Sau khi Bucket không còn đối tượng:

Quay lại danh sách Buckets.
Chọn Bucket của Cloud Office.
Chọn Delete.
Nhập tên Bucket để xác nhận.
Nhấn Delete bucket.
 3. Xóa S3 Gateway Endpoint

Mở Amazon VPC Console.

Chọn Endpoints.

Chọn Endpoint đã tạo

Nhấn Delete endpoint và xác nhận thao tác.

Sau khi xóa, Route Table sẽ tự động loại bỏ tuyến (Route) được tạo cho Gateway Endpoint.

4. Kiểm tra các tài nguyên còn lại

Kiểm tra lại các dịch vụ sau để đảm bảo không còn tài nguyên phát sinh từ workshop:

Amazon EC2
Amazon VPC Endpoints
Amazon S3 Buckets
Security Groups (nếu được tạo riêng)
CloudFormation Stack (nếu sử dụng để triển khai hạ tầng)

