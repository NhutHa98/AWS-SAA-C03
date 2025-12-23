# 🛡️ Amazon GuardDuty — Tổng quan ghi nhớ 3 giai đoạn

---

## ⚡ STAGE 1 — ULTRA-FAST READ (30–60s)

### 🧠 MEMORY ANCHORS

**GuardDuty là gì? (3 ý chính)**

* 🕵️ Dịch vụ **Threat Detection** được quản lý hoàn toàn bởi AWS
* 📊 Phân tích **logs + hành vi** bằng **Machine Learning**
* 🚨 Phát hiện sớm **security threats** trong AWS account

**🌍 Real-world analogy**

> GuardDuty giống như **camera an ninh thông minh** cho AWS account — không can thiệp, chỉ âm thầm quan sát và báo động khi có dấu hiệu bất thường.

**🔑 Must-remember keywords (≤7)**

* **Threat Detection**
* **Machine Learning**
* **Findings**

---

## 📝 STAGE 2 — PRE-EXAM READ

### 1️⃣ 🔍 SERVICE OVERVIEW

* **Amazon GuardDuty** là dịch vụ **managed security monitoring**
* Mục đích: phát hiện **malicious activity** & **unauthorized behavior**
* Giá trị cốt lõi: **No agents – No infrastructure – Continuous monitoring**

🧠 **Keywords**: **Threat Detection**, **Findings**, **Continuous monitoring**

---

### 2️⃣ 🛡️ THREATS / PROBLEMS IT SOLVES

**GuardDuty phát hiện gì?**

* 🔐 **Credential compromise** (access key bị lộ)
* 🌐 **Unusual API calls**
* 🧨 **Crypto mining**, **port scanning**, **malware behavior**

**Nếu KHÔNG dùng GuardDuty?**

* Không phát hiện sớm tấn công
* Phải tự phân tích log thủ công
* Dễ bỏ sót **low-and-slow attacks**

🧠 **Keywords**: **Threat**, **Detection**, **Risk**

---

### 3️⃣ 📦 USE CASES (REAL-WORLD)

**Khi nào dùng GuardDuty?**

* 🔎 Giám sát bảo mật cho toàn bộ AWS account
* 🏢 Enterprise cần **baseline security** nhanh
* 🧑‍💻 Security team muốn **early warning system**

**Best fit**

* Startup → bật nhanh, chi phí theo usage
* Enterprise → kết hợp với SOC / SIEM

🧠 **Keywords**: **Use case**, **Best fit**

---

### 4️⃣ 🧠 EXAM COVERAGE & TRAPS

**Exam tips**

* GuardDuty = **Detect**, KHÔNG phải **Prevent**
* Không cần cài agent
* Hoạt động **account-level**, không phải OS-level

**Anti-patterns**

* ❌ Dùng GuardDuty để block traffic
* ❌ Dùng để thay thế firewall

🧠 **Keywords**: **Exam tip**, **Anti-pattern**

---

## 📚 STAGE 3 — FULL UNDERSTANDING

### 5️⃣ 🧩 CORE COMPONENTS & ARCHITECTURE

**🔹 Data Sources**

* 📜 **CloudTrail logs**
* 🌐 **VPC Flow Logs**
* 🟣 **DNS logs**

**🔹 Analysis Engine**

* 🧠 **Machine Learning** + **Threat Intelligence**

**🔹 Output**

* 🚨 **Findings** (severity + description)

🧠 Keywords: **Logs 📜**, **ML 🧠**, **Findings 🚨**

---

### 6️⃣ 🔄 INTEGRATIONS & RELATED SERVICES

* **EventBridge** → trigger automation
* **Lambda** → auto-response
* **Security Hub** → centralize findings
* **SNS** → alert notification

🧠 **Keywords**: **Integration**, **Event-driven**, **Automation**

---

### 7️⃣ ⚖️ PROS & LIMITATIONS

**✅ Benefits**

* Không cần cấu hình phức tạp
* Phát hiện sớm, liên tục
* Scale tự động

**⚠️ Limitations**

* Không phản ứng tự động nếu không tích hợp thêm
* Có thể phát sinh chi phí nếu log volume lớn

🧠 **Keywords**: **Benefit**, **Limitation**

---

### 8️⃣ 🧪 SCENARIOS & DECISION GUIDE

**Choose GuardDuty when**

* Cần **visibility** về security threats
* Muốn giải pháp nhanh, managed

**Compare (high-level)**

* GuardDuty vs CloudWatch → security vs monitoring
* GuardDuty vs WAF → detect vs protect

🧠 **Keywords**: **Choose when**, **Compare**

---

📌 **ONE-LINE EXAM MEMORY**

> **Amazon GuardDuty = Managed Threat Detection using ML on AWS logs** 🧠🛡️
