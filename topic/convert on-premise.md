Dưới đây là **tổng hợp đầy đủ các dạng câu hỏi thường gặp** trong các bài thi AWS (SAA, SAP), phỏng vấn, hoặc bài tập kiến trúc — liên quan đến **convert on-premise → cloud**, **đồng bộ dữ liệu**, **di chuyển hệ thống**, **kết nối hybrid**, **DR**, và **migration patterns**.
Mình gom lại thành **nhóm rõ ràng**, dễ học, dễ áp dụng.

---

# 🧩 **1. Câu hỏi về Migration Strategy (6R – chuẩn AWS)**

Luôn xuất hiện khi nói “convert on-premise lên cloud”.

### 6R Migration Model:

1. **Rehost (Lift & Shift)** → dùng VPS EC2.
2. **Replatform (Lift & Tweak)** → dùng RDS, ECS, Elastic Beanstalk.
3. **Repurchase** → chuyển sang SaaS như Salesforce.
4. **Refactor / Re-architect** → microservices, serverless.
5. **Retire** → bỏ hệ thống không cần thiết.
6. **Retain** → giữ lại on-premise.

---

# 🔗 **2. Câu hỏi về Hybrid Connectivity (kết nối cloud ↔ on-premise)**

Đa phần hỏi về: **VPN, Direct Connect, Transit Gateway**.

### Nội dung thường gặp:

* Kết nối site-to-site VPN giữa on-premise và AWS VPC.
* Direct Connect khi cần:

  * bandwidth cao
  * latency thấp
  * truyền dữ liệu liên tục
* Kết hợp Direct Connect + VPN cho HA (DX primary, VPN backup).
* Kết nối multi-site → dùng Transit Gateway.

---

# 🔁 **3. Câu hỏi về Đồng bộ dữ liệu (Data Synchronization)**

Nhóm này cực phổ biến.

### Các dịch vụ giải bài:

* **AWS DMS** → sync database.
* **AWS SCT** → convert schema.
* **AWS DataSync** → transfer file trong NAS, NFS, SMB, EFS, S3.
* **S3 Transfer Acceleration** → sync từ nhiều region.
* **Snowball / Snowmobile** → sync data lớn offline.

### Chủ đề thường gặp:

* Đồng bộ database on-prem → AWS RDS mà không downtime.
* Sync file giữa on-prem NAS ↔ S3.
* Di chuyển petabytes dữ liệu (Snow family).
* One-time migration vs continuous replication.

---

# 🛠️ **4. Câu hỏi về “Convert app lên cloud” (App Modernization)**

Thường phân loại theo workload:

### Ứng dụng web:

* Migrate IIS/Apache/Nginx → EC2 + ALB.
* Migrate sang serverless → Lambda + API Gateway.

### Ứng dụng container:

* Convert on-prem Kubernetes → EKS/ECS.

### Ứng dụng monolith → microservices:

* Tách thành Lambda/ECS + EventBridge + SQS.

### Windows workloads:

* Chuyển AD lên AWS Managed AD.
* Chuyển SQL Server lên RDS SQL Server.

### Legacy app:

* Rehost → EC2 + ASG + EBS.
* Replatform → RDS + ElastiCache.

---

# 🗄️ **5. Câu hỏi về Backup – Restore – DR giữa On-premise ↔ Cloud**

Một dạng cực hay ra.

### Các mô hình DR:

* **Pilot Light** → chỉ giữ core systems warm.
* **Warm Standby** → app chạy ở mức tối thiểu.
* **Multi-site Active/Active** → full HA.

### Dịch vụ thường xuất hiện:

* AWS Backup
* AWS Storage Gateway (Tape, File, Volume)
* CloudEndure (AWS MGN) để migrate VM
* Route 53 failover routing

---

# 🛣️ **6. Câu hỏi về Identity / Directory đồng bộ Cloud – On-premise**

Các bài thường hỏi về:

### Active Directory:

* AWS Managed AD
* AD Connector
* MFA federation (Azure AD, Okta…)

### SSO:

* AWS IAM Identity Center
* SAML 2.0 between on-prem and AWS

---

# 📡 **7. Câu hỏi về Network Migration**

Hay gặp dạng:

* Chuyển network on-prem lên VPC structure.
* Nối nhiều VPC với on-prem → Transit Gateway.
* NAT vs IGW vs Private/Public subnet khi convert.

---

# 📦 **8. Câu hỏi về Storage Migration**

Phổ biến:

* On-prem backup to S3.
* NFS on-prem → EFS.
* SMB on-prem → FSx for Windows.
* Hệ thống sử dụng shared drive → EFS/FSx.
* Object storage on-prem → S3.

---

# 🧭 **9. Câu hỏi về Security khi migrate lên AWS**

Thường hỏi:

### IAM:

* Tách quyền, least privilege.

### Encryption:

* Dùng KMS, CMK.

### Logging:

* CloudTrail, Config, GuardDuty.

### Boundary:

* Network ACL, SG, WAF, Shield.

---

# 🧰 **10. Các dạng câu hỏi đặc biệt**

Thi thoảng xuất hiện:

* Convert batch job on-prem → AWS Batch.
* Convert cron job → EventBridge + Lambda.
* Convert messaging Kafka → MSK / Kinesis.
* Convert file processing pipeline → S3 + Lambda + Step Functions.

---

# 📌 TÓM TẮT NHANH (để học thuộc)

**Các nhóm câu hỏi convert on-premise → cloud gồm:**

1. **Migration strategy (6R).**
2. **Hybrid network (VPN, DX, TGW).**
3. **Data sync/migration (DMS, DataSync, Snow).**
4. **Application modernization (EC2/ECS/Lambda).**
5. **Backup – DR – HA.**
6. **Directory & identity sync.**
7. **Network architecture migration.**
8. **Storage migration.**
9. **Security khi migrate.**
10. **Các hệ thống đặc thù (batch, cron, Kafka…).**

---

Nếu bạn muốn mình **tạo bộ câu hỏi + đáp án mẫu** cho từng dạng (giống format bài thi AWS), mình có thể làm luôn.
