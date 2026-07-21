---
title : "Kiểm tra Interface Endpoint"
date : 2024-01-01
weight : 3
chapter : false
pre : " <b> 5.4.3 </b> "
---

Sau khi Endpoint có trạng thái Available, tiến hành kiểm tra.

Mở

AWS Systems Manager

↓

Session Manager

↓

Kết nối tới

CloudOffice-Backend

Sau khi đăng nhập thành công, chạy lệnh

aws ssm describe-instance-information

Nếu lệnh trả về thông tin của EC2, chứng tỏ Backend Server đã truy cập thành công dịch vụ AWS thông qua Interface Endpoint.


