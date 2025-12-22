# AWS IAM – Role, Permission & Resource (Cheat Sheet)

Tài liệu tóm tắt ngắn gọn để **ghi nhớ – ôn thi – áp dụng thực tế** về IAM trên AWS.

---

## 1. Các khái niệm cốt lõi

### IAM Role

* Là **danh tính (identity)** dùng cho **AWS service hoặc workload**
* Không có access key cố định
* Được **assume** tạm thời (STS)

> 👉 Role dùng cho *service*, không dùng cho *con người*

---

### Permission (Quyền)

* Được định nghĩa bằng **Policy JSON**
* Quyết định **được làm gì (Action)** trên **tài nguyên nào (Resource)**

Cấu trúc cơ bản:

```json
{
  "Effect": "Allow",
  "Action": "service:Action",
  "Resource": "arn:aws:service:..."
}
```

---

### Resource

* Là **đối tượng AWS cụ thể** (S3 bucket, DB, Queue…)
* Được xác định bằng **ARN**
* Không phải service nào cũng hỗ trợ resource-level permission

---

## 2. Action (quyền) – điều cần nhớ nhất

### Action KHÔNG tự định nghĩa

* Action do **AWS định nghĩa sẵn**
* Cú pháp cố định:

```
service:Action
```

Ví dụ:

* `s3:GetObject`
* `ec2:StartInstances`
* `dynamodb:Query`

🚫 Không thể tự tạo action mới

---

## 3. Policy – thứ bạn tự viết

Bạn **tự define policy**, nhưng **chọn action từ AWS**.

### Các loại policy

* **AWS Managed Policy** (AWS tạo)
* **Customer Managed Policy** (bạn tạo)
* **Inline Policy** (gắn trực tiếp vào role)

---

## 4. Các loại quyền trong IAM

### 4.1 Identity-based permission ⭐

* Gắn vào: **User / Group / Role**
* Phổ biến nhất

---

### 4.2 Resource-based permission

* Gắn trực tiếp lên resource
* Ví dụ:

  * S3 Bucket Policy
  * SQS Queue Policy

---

### 4.3 Permission Boundary

* Giới hạn **trần quyền** của role/user
* Không cấp thêm quyền

---

### 4.4 Session-based permission

* Quyền tạm thời (STS, AssumeRole, SSO)

---

### 4.5 Service Control Policy (SCP)

* Áp dụng cho **Account / OU**
* Dùng trong **AWS Organizations**
* Chỉ giới hạn, không cấp quyền

---

## 5. Thứ tự đánh giá quyền (RẤT QUAN TRỌNG)

1. **Explicit Deny** → chặn ngay
2. **Allow**
3. **Implicit Deny** (mặc định)

> Chỉ cần **1 deny** là chặn tất cả

---

## 6. Các IAM Role phổ biến cần nhớ

| Tình huống                 | IAM Role                      |
| -------------------------- | ----------------------------- |
| EC2 truy cập AWS           | EC2 Instance Role             |
| Lambda truy cập AWS        | Lambda Execution Role         |
| ECS Container truy cập AWS | ECS Task Role (`taskRoleArn`) |
| ECS Agent                  | ECS Execution Role            |
| CI/CD                      | OIDC / Pipeline Role          |
| Cross-account              | Assume Role                   |

---

## 7. Role vs Resource – dễ nhầm

| Thành phần | Câu hỏi trả lời    |
| ---------- | ------------------ |
| Role       | *Ai được làm?*     |
| Action     | *Được làm gì?*     |
| Resource   | *Làm trên cái gì?* |

---

## 8. Nguyên tắc vàng khi dùng IAM

* **Least Privilege**
* Mỗi service → **1 role riêng**
* Không dùng IAM User cho application
* Tránh `Action: "*"`, `Resource: "*"`

---

## 9. Một câu chốt để nhớ lâu

> **AWS định nghĩa Action, bạn định nghĩa Policy, Role quyết định ai được dùng Policy đó trên Resource nào.**

# IAM User vs IAM Role (exam table)
| Use case             | IAM User | IAM Role |
| -------------------- | -------- | -------- |
| Human login          | ✅        | ❌        |
| EC2/Lambda access    | ❌        | ✅        |
| Cross-account access | ❌        | ✅        |
| Temporary creds      | ❌        | ✅        |
| SaaS integration     | ❌        | ✅        |
| Best practice        | ⚠️       | ⭐        |
