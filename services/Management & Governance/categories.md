
### 1️⃣ **Account & Organization Management (Quản lý account & quyền truy cập)**

| Dịch vụ               | Use Case thực tế                                                              | Ghi chú                                    |
| --------------------- | ----------------------------------------------------------------------------- | ------------------------------------------ |
| **AWS Organizations** | Tạo nhiều account con, quản lý billing tập trung, apply SCP để giới hạn quyền | Multi-account setup, billing consolidation |
| **Control Tower**     | Triển khai landing zone chuẩn, áp dụng guardrails                             | Multi-account setup theo best practice     |


**Đề thi hay hỏi:** "Bạn cần quản lý 5 account con với các guardrails bảo mật → dùng gì?"

---

### 2️⃣ **Monitoring & Observability (Giám sát & cảnh báo)**

| Dịch vụ               | Use Case thực tế                                        | Ghi chú                            |
| --------------------- | ------------------------------------------------------- | ---------------------------------- |
| **CloudWatch**        | Giám sát EC2/ECS/Lambda, alert CPU high, custom metrics | Dashboard & alarms                 |
| **Amazon Grafana**    | Visualization metrics multi-source                      | Kết hợp với CloudWatch, Prometheus |
| **Amazon Prometheus** | Container metrics, alerting                             | Time-series metrics                |

**Đề thi hay hỏi:** "Thiết lập alert khi Lambda function lỗi > 5 lần/phút → chọn dịch vụ nào?"

---

### 3️⃣ **Logging & Auditing (Theo dõi hoạt động & compliance)**


| Dịch vụ             | Mục đích chính                 | Phạm vi                           | Điểm đặc trưng / Ghi chú                                                                                                                     |
| ------------------- | ------------------------------ | --------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **CloudFormation**  | Triển khai hạ tầng (IaC)       | Multi-resource AWS stack          | - Infrastructure as Code (YAML/JSON) <br> - Tự động tạo EC2, VPC, RDS, Lambda… <br> - Drift detection, stack update                          |
| **AWS Proton**      | Triển khai ứng dụng chuẩn hóa  | Container & Serverless            | - Template-driven CI/CD <br> - Tạo môi trường dev/test/prod chuẩn <br> - Tập trung vào **ứng dụng**, không chỉ hạ tầng                       |
| **Launch Wizard**   | Triển khai workloads Microsoft | SQL Server, SAP, Active Directory | - Wizard hướng dẫn từng bước <br> - ước lượng chi phí <br> - Dùng cho **ứng dụng enterprise** sẵn có                                         |
| **Systems Manager** | Quản lý & vận hành tài nguyên  | EC2 & on-premises                 | - Patch management, run commands <br> - Automation scripts <br> - Session Manager remote access <br> - Hỗ trợ vận hành, không chỉ triển khai |

---

### 💡 Mẹo nhớ nhanh cho thi

* **CloudFormation** → IaC, triển khai **hạ tầng**.
* **Proton** → triển khai **ứng dụng container/serverless** theo template chuẩn.
* **Launch Wizard** → triển khai **Microsoft workloads** theo wizard.
* **Systems Manager** → **quản lý & vận hành**, patch, remote command.


**Đề thi hay hỏi:** "Xác định ai đã xóa S3 bucket → dùng gì?"


---

### 4️⃣ **Automation & Deployment (Triển khai & tự động hóa)**

| Dịch vụ             | Use Case thực tế                             | Ghi chú                      |
| ------------------- | -------------------------------------------- | ---------------------------- |
| **CloudFormation**  | Deploy multi-resource stack                  | IaC, YAML/JSON templates     |
| **AWS Proton**      | Deploy container/serverless chuẩn hóa        | Template-driven CI/CD        |
| **Launch Wizard**   | Deploy Microsoft workloads (SQL Server, SAP) | Wizard & cost estimate       |
| **Systems Manager** | Patch management, remote command, automation | EC2/on-prem, Session Manager |

**Đề thi hay hỏi:** "Triển khai ứng dụng multi-tier reproducible → dùng gì?"

---

### 5️⃣ **Optimization & Cost Management (Tối ưu & chi phí)**

| Dịch vụ                   | Use Case thực tế                         | Ghi chú                |
| ------------------------- | ---------------------------------------- | ---------------------- |
| **Trusted Advisor**       | Optimize cost, security, fault tolerance | 5 categories           |
| **AWS Compute Optimizer** | Đề xuất resizing EC2/EBS/Lambda          | Dựa trên usage pattern |
| **Service Quotas**        | Track & request quota increases          | Hạn chế vượt limit     |

**Đề thi hay hỏi:** "Chi phí EC2 tăng → dùng tool nào để nhận recommendation?"

---

### 6️⃣ **Incident & Resilience Management**

| Dịch vụ                | Use Case thực tế                                 | Ghi chú                          |
| ---------------------- | ------------------------------------------------ | -------------------------------- |
| **Incident Manager**   | Quản lý incident, alert team                     | Tích hợp CloudWatch & SNS        |
| **AWS Resilience Hub** | Đánh giá & cải thiện khả năng phục hồi workloads | Simulate failure, recommendation |

**Đề thi hay hỏi:** "Ứng dụng critical failure → tự động alert & response plan → dùng gì?"

---

### 7️⃣ **Resource & License Management**

| Dịch vụ                          | Use Case thực tế                 | Ghi chú                                          |
| -------------------------------- | -------------------------------- | ------------------------------------------------ |
| **Resource Groups & Tag Editor** | Quản lý tag, tìm & apply tags    | Useful for cost allocation & resource management |
| **AWS License Manager**          | Track software license           | BYOL & compliance                                |
| **AWS Service Catalog**          | Standardize products & templates | Limit users deploy only approved resources       |
| **AWS Resource Explorer**        | Tìm kiếm tài nguyên              | Multi-region                                     |

**Đề thi hay hỏi:** "Chỉ cho phép dev deploy EC2 chuẩn → dùng gì?"

---

💡 **Tóm lại:**
Các use case trong đề SAA-C03/SAA-C02 thường xoay quanh:

1. **Multi-account setup & governance** → Organizations, Control Tower
2. **Monitoring & alerting** → CloudWatch, Prometheus, Grafana
3. **Audit & compliance** → CloudTrail, Config, Health Dashboard
4. **Infrastructure deployment & automation** → CloudFormation, Proton, Launch Wizard, Systems Manager
5. **Optimization & cost** → Trusted Advisor, Compute Optimizer, Service Quotas
6. **Incident & resilience** → Incident Manager, Resilience Hub
7. **Resource & license management** → Resource Groups, License Manager, Service Catalog

