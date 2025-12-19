

### **Định nghĩa**

**Guardrail** = tập hợp **chính sách bảo vệ (policies)** được áp dụng cho các **AWS account trong landing zone**, nhằm đảm bảo rằng các account luôn tuân thủ **best practices** về **security, compliance, và operations**.

---

### **Các loại guardrail**

1. **Preventive (Ngăn chặn)**

* Ngăn người dùng thực hiện hành động vi phạm policy.
* Ví dụ: “Không cho phép public S3 bucket” → nếu cố gắng tạo bucket public, bị block ngay.

2. **Detective (Phát hiện)**

* Cho phép hành động xảy ra nhưng sẽ báo cáo vi phạm.
* Ví dụ: “Kiểm tra tất cả EC2 không tuân thủ tagging rules” → phát hiện & log violation.

---

### **Use Case thực tế**

* Triển khai **multi-account AWS** cho công ty, muốn **đảm bảo tất cả account con không vượt quá quyền hạn**, không public S3, EC2 phải tag đúng, log phải bật.
* Guardrails giúp **tự động enforce hoặc detect các policy này**, giảm rủi ro con người.

---

💡 **Ghi nhớ cho thi:**

* **Control Tower = Landing Zone setup + Guardrails**
* **Guardrails** = policies **preventive hoặc detective**
* Câu hỏi thường kiểu:

> “Bạn cần triển khai multi-account với best practices và hạn chế public S3 bucket. Dùng gì?” → **Control Tower + guardrails preventive**
