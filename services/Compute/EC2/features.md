## ENI
💡 ENI (Elastic Network Interface) là **card mạng ảo trong VPC**, cung cấp IP, MAC và gắn Security Group cho tài nguyên.

➡️ Dùng với **EC2** để **multi-network**, **failover nhanh**, **giữ nguyên IP** bằng cách detach/attach ENI.

📝 Nhiều dịch vụ AWS **có ENI bên dưới**, nhưng **chỉ EC2 cho quản lý ENI trực tiếp** (cùng AZ, cùng VPC).

## Amazon Data Lifecycle Manager (DLM) 

**1️⃣ Định nghĩa**
Amazon DLM là dịch vụ **tự động hóa vòng đời snapshot** cho **EBS volumes / EBS-backed AMI**, giúp tạo, giữ và xóa snapshot theo policy.

**2️⃣ Use case**

* Backup **EC2 EBS volumes** định kỳ
* Quản lý snapshot **tự động, không thủ công**
* Đảm bảo **backup compliance** cho EC2

**3️⃣ Ghi chú**

* **Chỉ áp dụng cho EBS**, không dùng cho RDS/DynamoDB
* Dựa trên **tag-based policy**
* Không hỗ trợ restore (chỉ quản lý snapshot lifecycle)
