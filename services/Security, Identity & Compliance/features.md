### **VPC Endpoint**

**1️⃣ Định nghĩa**
VPC Endpoint cho phép **kết nối private từ VPC tới dịch vụ AWS** (S3, DynamoDB, SNS, SQS, RDS API…) **không đi Internet**, không cần NAT hay IGW.

**2️⃣ Use case**

* EC2 / ECS / Lambda trong **private subnet**
* Truy cập S3, DynamoDB, SQS… **an toàn & ổn định**
* Giảm chi phí NAT Gateway, tăng bảo mật

**3️⃣ Ghi chú**

* Có 2 loại:

  * **Gateway Endpoint**: S3, DynamoDB (miễn phí)
  * **Interface Endpoint (PrivateLink)**: hầu hết dịch vụ khác (tốn phí)
* Không dùng cho public internet
* Quan trọng với kiến trúc **private-only VPC**
