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

### AWS Systems Manager Parameter Store 

**1️⃣ Định nghĩa**
Parameter Store là dịch vụ **lưu trữ và quản lý cấu hình/secret tập trung** (key–value), tích hợp với IAM để kiểm soát truy cập và hỗ trợ mã hóa bằng KMS.

**2️⃣ Use case**

* Lưu **config**, **feature flag**, **secret** (DB endpoint, API key…)
* Truy cập an toàn từ **EC2 / ECS / Lambda**
* Quản lý cấu hình theo **environment** (dev/staging/prod)

**3️⃣ Ghi chú**

* Có **Standard** (miễn phí, giới hạn) và **Advanced** (tốn phí, nhiều tính năng hơn)
* Không có rotation tự động như Secrets Manager
* Phù hợp config/secret **ít thay đổi**
### **AWS Direct Connect **

**1️⃣ Định nghĩa**
AWS Direct Connect là **kết nối mạng riêng (dedicated)** từ hạ tầng on-premise/data center của bạn **trực tiếp tới AWS**, không đi qua Internet công cộng.

**2️⃣ Use case**

* Hybrid cloud (on-prem ↔ AWS)
* Workload cần **băng thông ổn định, latency thấp**
* Truyền dữ liệu lớn, liên tục (backup, big data, media)

**3️⃣ Ghi chú**

* Không tự động mã hóa (thường kết hợp **VPN over Direct Connect**)
* Thiết lập mất thời gian, chi phí cao
* Không thay thế VPN, thường dùng **song song để HA**
