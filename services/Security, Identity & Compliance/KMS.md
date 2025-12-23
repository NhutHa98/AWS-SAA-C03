AWS Key Management Service (KMS)

==============================
⚡ **STAGE 1 — ULTRA-FAST READ (30–60s)**
========================================

🧠 **MEMORY ANCHORS**

🔑 **KMS là gì? (siêu ngắn)**

* Dịch vụ **quản lý encryption key tập trung** 🔐
* Kiểm soát **ai dùng key – dùng khi nào – dùng ở đâu**
* Tích hợp sẵn với hầu hết dịch vụ AWS

🏠 **Real-world analogy**

* KMS giống như **phòng két ngân hàng** 🏦:
  bạn không giữ tiền (data), chỉ **quản lý chìa khóa** để mở két.

🧠 **Must-remember keywords**

* **Encryption**
* **CMK**
* **IAM**
* **Audit**

---

==============================
📝 **STAGE 2 — PRE-EXAM READ**
==============================

1️⃣ 🔍 **SERVICE OVERVIEW**

* **KMS** là dịch vụ quản lý **encryption key** được AWS quản lý hoàn toàn
* Mục tiêu: **bảo vệ data at rest & in transit**
* Giá trị cốt lõi:

  * Centralized key management
  * Fine-grained access control
  * Native AWS integration

🧠 Keywords: **Encryption**, **Key**, **Access control**, **Audit**

---

2️⃣ 🛡️ **THREATS / PROBLEMS IT SOLVES**

* Rủi ro khi tự quản lý key:

  * Key bị leak
  * Không audit được ai đã dùng key
  * Quản lý key thủ công → lỗi con người

* Nếu **không dùng KMS**:

  * Encryption yếu / không đồng bộ
  * Khó đạt compliance (PCI, HIPAA, ISO)

🧠 Keywords: **Threat**, **Risk**, **Compliance**

---

3️⃣ 📦 **USE CASES (REAL-WORLD)**

* Encrypt dữ liệu trong:

  * S3, EBS, RDS, DynamoDB
* Bảo vệ secrets, token, credentials
* Doanh nghiệp cần compliance & audit trail

👥 Phù hợp cho:

* Startup (dùng default)
* Enterprise (custom key, strict policy)
* Security team

🧠 Keywords: **Use case**, **Best fit**

---

4️⃣ 🧠 **EXAM COVERAGE & TRAPS**

✅ Exam loves:

* Encryption **at rest** → nghĩ tới **KMS**
* AWS-managed vs Customer-managed key
* IAM policy + Key policy

❌ Traps thường gặp:

* KMS **KHÔNG lưu data**
* KMS **KHÔNG phải secrets manager**
* KMS **KHÔNG encrypt file lớn trực tiếp**

🧠 Keywords: **Exam tip**, **Anti-pattern**

---

==============================
📚 **STAGE 3 — FULL UNDERSTANDING**
===================================

5️⃣ 🧩 **CORE COMPONENTS & ARCHITECTURE**

🔑 **CMK (Customer Master Key)**

* Key logic trung tâm
* Có thể do AWS hoặc customer quản lý

📜 **Key Policy**

* Ai được dùng key
* Mandatory (khác IAM)

👤 **IAM Policy**

* Quyền sử dụng KMS API

📊 **CloudTrail**

* Audit mọi hành động với key

🧠 Keywords: **CMK** 🔑 | **Policy** 📜 | **Audit** 📊

---

6️⃣ 🔄 **INTEGRATIONS & RELATED SERVICES**

* S3 → encrypt object
* EBS → encrypt volume
* RDS → encrypt database
* DynamoDB → encrypt table
* Secrets Manager → dùng KMS để encrypt secrets

🧠 Keywords: **Integration**, **Automation**

---

7️⃣ ⚖️ **PROS & LIMITATIONS**

✅ Pros

* Fully managed
* Secure by default
* Strong compliance support

⚠️ Limitations

* Có chi phí per key & per request
* Region-scoped (không global)
* Không dùng để encrypt data lớn trực tiếp

🧠 Keywords: **Benefit**, **Limitation**

---

8️⃣ 🧪 **SCENARIOS & DECISION GUIDE**

👉 Chọn **KMS** khi:

* Cần encryption + access control
* Cần audit key usage
* Dùng dịch vụ AWS native

🔄 So sánh nhanh:

* KMS vs Secrets Manager → key vs secret
* KMS vs CloudHSM → managed vs self-managed HSM

🧠 Keywords: **Choose when**, **Compare**

S3 + KMS = encrypt khi upload, auto decrypt khi download, không gọi kms decrypt trực tiếp

With SSE-KMS, Amazon S3 transparently encrypts and decrypts objects by calling AWS KMS on behalf of the user.

Encryption protects data at rest, in transit, and ensures data is only decrypted for authorized access.