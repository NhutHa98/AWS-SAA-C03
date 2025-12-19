Ok, làm ngay một **bảng so sánh “nhìn là nhớ”** cho nhóm **🔐 Security, Identity & Compliance** của AWS nha.
Mình **phân loại bằng emoji theo use case chính** để bạn học/ôn thi SAA hoặc design system dễ hơn 👌

---

## 🔐 Security, Identity & Compliance – Quick Compare

### 🧑‍💼 **Identity & Access Management**
| Dịch vụ                            | Định nghĩa                         | Use case                          | Ghi chú              |
| ---------------------------------- | ---------------------------------- | --------------------------------- | -------------------- |
| 🧑‍💻 **IAM**                      | Quản lý user, role, policy cho AWS | Phân quyền truy cập AWS resources | Global service       |
| 🏢 **IAM Identity Center**         | SSO cho nhân viên                  | Login nhiều account AWS           | Thay AWS SSO         |
| 👥 **Amazon Cognito**              | Identity cho **end-user app**      | Signup / Login / MFA              | JWT, social login    |
| 🔑 **Amazon Verified Permissions** | Authorization policy (Cedar)       | Fine-grained auth cho app         | Tách authZ khỏi code |
| 📁 **Directory Service**           | Managed Active Directory           | Join EC2 vào domain               | Hybrid AD            |

---

### 🔐 **Secrets, Keys & Cryptography**

| Dịch vụ                         | Định nghĩa                        | Use case thực tế           | Ghi chú                         |
| ------------------------------- | --------------------------------- | -------------------------- | ------------------------------- |
| 🤫 **Secrets Manager**          | Lưu secret (DB password, API key) | Rotate secret tự động      | Có cost theo secret             |
| 🔐 **KMS**                      | Quản lý encryption key            | Encrypt S3, EBS, RDS       | Hỗ trợ CMK, envelope encryption |
| 🧱 **CloudHSM**                 | HSM vật lý dedicated              | Compliance cao (PCI, FIPS) | Bạn tự quản key hoàn toàn       |
| 💳 **AWS Payment Cryptography** | Crypto cho thanh toán             | Xử lý thẻ, PIN, EMV        | Dành cho fintech                |
| ✍️ **AWS Signer**               | Ký code                           | Lambda, IoT firmware       | Tránh code bị chỉnh sửa         |

---

### 📜 **Certificates & PKI**

| Dịch vụ                          | Định nghĩa                    | Use case thực tế          | Ghi chú          |
| -------------------------------- | ----------------------------- | ------------------------- | ---------------- |
| 📜 **Certificate Manager (ACM)** | SSL/TLS cert managed          | HTTPS cho ALB, CloudFront | Free public cert |
| 🏛 **AWS Private CA**            | Private Certificate Authority | Cert nội bộ (mTLS)        | Có phí theo CA   |

---

### 🛡 **Threat Detection & Vulnerability**

| Dịch vụ                                  | Định nghĩa                 | Use case thực tế             | Ghi chú            |
| ---------------------------------------- | -------------------------- | ---------------------------- | ------------------ |
| 🚨 **GuardDuty**                         | Threat detection           | Phát hiện account compromise | ML + logs          |
| 🧪 **Amazon Inspector**                  | Vulnerability scanning     | Scan EC2, ECR image          | Tự động            |
| 🕵️ **Amazon Macie**                     | Discover sensitive data    | Detect PII trong S3          | GDPR, compliance   |
| 🔍 **Detective**                         | Điều tra security incident | Phân tích root cause         | Dựa trên GuardDuty |
| 🧑‍🚒 **AWS Security Incident Response** | Managed IR service         | Xử lý incident nghiêm trọng  | Có chuyên gia AWS  |

---

### 🔥 **Network & Application Protection**

| Dịch vụ                              | Định nghĩa                   | Use case thực tế         | Ghi chú                 |
| ------------------------------------ | ---------------------------- | ------------------------ | ----------------------- |
| 🧱 **WAF**                           | Web Application Firewall     | Chặn SQLi, XSS           | Gắn với ALB, CloudFront |
| 🛡 **Shield**                        | DDoS protection              | Bảo vệ app public        | Standard miễn phí       |
| 🧯 **AWS Firewall Manager**          | Quản lý firewall tập trung   | Multi-account WAF/Shield | Dùng với Organizations  |
| 🔒 **Resource Access Manager (RAM)** | Share resource cross-account | Share VPC, Subnet        | Không copy resource     |

---

### 📊 **Security Posture, Audit & Compliance**

| Dịch vụ                   | Định nghĩa                  | Use case thực tế         | Ghi chú                      |
| ------------------------- | --------------------------- | ------------------------ | ---------------------------- |
| 📊 **Security Hub**       | Central security view       | Tổng hợp finding         | Chuẩn CIS, PCI               |
| 🧾 **Security Hub CSPM**  | Cloud Security Posture Mgmt | Đánh giá config sai      | Part of Security Hub         |
| 🧪 **AWS Audit Manager**  | Audit evidence tự động      | Chuẩn bị audit           | PCI, SOC                     |
| 📦 **AWS Artifact**       | Compliance reports          | Tải SOC, ISO             | Không phải tool bảo vệ       |
| 🗂 **Security Lake**      | Data lake security          | Phân tích log bảo mật    | Chuẩn OCSF                   |
| 🤖 **AWS Security Agent** | Agent bảo mật workload      | Thu thập security signal | Phục vụ Inspector, GuardDuty |

---

## 🧠 Mẹo nhớ nhanh cho thi & design

* **AuthN/AuthZ** 👉 IAM, Identity Center, Verified Permissions
* **Encrypt** 👉 KMS (default), CloudHSM (compliance cao)
* **Detect threat** 👉 GuardDuty (real-time), Inspector (vuln), Macie (PII)
* **Protect app** 👉 WAF + Shield
* **Compliance & audit** 👉 Security Hub, Audit Manager, Artifact
🧠 Ghi nhớ nhanh (rất hay ra thi)

End-user login → 👥 Cognito

AWS access → 🧑‍💻 IAM

Nhân viên công ty → 🏢 Identity Center

AuthZ phức tạp → 🔑 Verified Permissions

|              | Cognito           | IAM               | IAM Identity Center |
| ------------ | ----------------- | ----------------- | ------------------- |
| Đối tượng    | End-user app      | AWS admin/service | Nhân viên           |
| UI login     | ✅                 | ❌                 | ✅                   |
| JWT          | ✅                 | ❌                 | ⚠️                  |
| Social login | ✅                 | ❌                 | ❌                   |
| AWS access   | Qua Identity Pool | Trực tiếp         | Trực tiếp           |
