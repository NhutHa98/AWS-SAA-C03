# AWS Config

🎯 **Mục tiêu**: Hiểu nhanh – nhớ lâu – làm bài exam không dính bẫy

==============================
⚡ STAGE 1 — ULTRA-FAST READ (30–60s)
====================================

🧠 **MEMORY ANCHORS**

🔹 AWS Config là gì?

* 📸 **Chụp snapshot** cấu hình tài nguyên AWS
* 🕰️ **Theo dõi thay đổi** theo thời gian
* 📏 **So sánh với rule** để kiểm tra compliance

🔹 Ví von đời thực:

* AWS Config giống như **camera an ninh + nhật ký thay đổi** cho hạ tầng AWS 🕵️‍♂️📒

🔹 Must-remember keywords:

* **Configuration**
* **Compliance**
* **Change tracking**

==============================
📝 STAGE 2 — PRE-EXAM READ
==========================

1️⃣ 🔍 SERVICE OVERVIEW

* **AWS Config** là dịch vụ **record & evaluate** cấu hình tài nguyên AWS
* WHY: Biết **ai – khi nào – thay đổi gì** trong hạ tầng
* Value: Audit, compliance, troubleshooting cực mạnh
* 🧠 Keywords: **Configuration**, **Compliance**, **Audit**

2️⃣ 🛡️ THREATS / PROBLEMS IT SOLVES

* Drift cấu hình (manual change, human error)
* Vi phạm policy (public S3, open SG)
* Không truy vết được thay đổi khi có sự cố
* Không dùng Config → ❌ Mù lịch sử thay đổi
* 🧠 Keywords: **Risk**, **Detection**, **Drift**

3️⃣ 📦 USE CASES (REAL-WORLD)

* Audit bảo mật (ISO, SOC, PCI)
* Theo dõi config EC2, S3, IAM, SG
* Trigger auto-fix khi vi phạm rule
* Best cho: **Enterprise**, **Security team**, **Regulated workload**
* 🧠 Keywords: **Use case**, **Best fit**

4️⃣ 🧠 EXAM COVERAGE & TRAPS

* Config ≠ CloudTrail ❌
* Config không monitor performance ❌
* Dùng khi đề bài nhắc: *history*, *compliance*, *configuration change*
* 🧠 Keywords: **Exam tip**, **Anti-pattern**

==============================
📚 STAGE 3 — FULL UNDERSTANDING
===============================

5️⃣ 🧩 CORE COMPONENTS & ARCHITECTURE

* 📸 **Configuration Recorder**: Ghi lại config resource
* 📜 **Configuration History**: Lịch sử thay đổi
* 📏 **Config Rules**: Check compliance
* 📊 **Compliance Dashboard**: Tổng quan trạng thái
* 🧠 Keywords: **Recorder**, **Rule**, **History**

6️⃣ 🔄 INTEGRATIONS & RELATED SERVICES

* **CloudTrail**: Ai thực hiện thay đổi
* **CloudWatch Events / EventBridge**: Trigger automation
* **Lambda**: Auto-remediation
* **SNS**: Alert
* 🧠 Keywords: **Integration**, **Event-driven**, **Automation**

7️⃣ ⚖️ PROS & LIMITATIONS

✅ Pros

* Theo dõi thay đổi chi tiết
* Compliance mạnh
* Audit-friendly

⚠️ Limitations

* Không real-time (near real-time)
* Không thay CloudTrail
* Tính phí theo rule & record
* 🧠 Keywords: **Benefit**, **Limitation**

8️⃣ 🧪 SCENARIOS & DECISION GUIDE

✔️ Chọn AWS Config khi:

* Cần history cấu hình
* Cần compliance / audit

❌ Không chọn khi:

* Chỉ cần log API → dùng CloudTrail
* Chỉ cần metric / alarm → dùng CloudWatch

🧠 Keywords: **Choose when**, **Compare**

==============================
📌 ONE-LINE EXAM SUMMARY
========================

👉 **AWS Config = Configuration history + Compliance checking**



==============================
MORE
========================

## 🔧 **Muốn SỬA cấu hình → gọi ai?**

👉 **AWS Lambda**
👉 **AWS Systems Manager Automation (SSM Automation)**

---

## 🧠 Công thức “chuẩn sách giáo khoa”

```
AWS Config (detect)
   ↓
EventBridge
   ↓
Lambda / SSM Automation (fix)
```

---

## 📌 Khi nào gọi cái nào?

### 🧠 **Lambda**

* Logic custom
* Viết code xử lý phức tạp
* Exam hay gặp nhất ✅

### ⚙️ **SSM Automation**

* Có sẵn runbook (AWS-managed)
* Fix chuẩn, ít code
* Hay dùng cho security baseline

---

## ❌ KHÔNG BAO GIỜ là

* AWS Config ❌
* CloudTrail ❌
* CloudWatch ❌

---

## 🧠 Câu học thuộc (ăn điểm exam)

> **AWS Config detects non-compliance and triggers remediation using Lambda or SSM Automation.**

