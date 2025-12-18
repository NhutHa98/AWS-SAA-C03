

## 🪣 Amazon S3 Storage Classes (Tiers)

### 📦 Core / Frequent Access

| Tier                       | Use case                           | Notes                                 | Emoji |
| -------------------------- | ---------------------------------- | ------------------------------------- | ----- |
| **S3 Standard**            | Frequently accessed data           | High availability, low latency        | ⚡     |
| **S3 Intelligent-Tiering** | Unknown / changing access patterns | Auto moves data, small monitoring fee | 🤖    |

---

### 📉 Infrequent Access

| Tier               | Use case                   | Notes                             | Emoji |
| ------------------ | -------------------------- | --------------------------------- | ----- |
| **S3 Standard-IA** | Infrequent but fast access | Retrieval fee                     | 📉    |
| **S3 One Zone-IA** | Infrequent + non-critical  | Single AZ (cheaper, less durable) | 🧭    |

---

### 🧊 Archive (Glacier family)

| Tier                              | Retrieval time | Use case                              | Emoji |
| --------------------------------- | -------------- | ------------------------------------- | ----- |
| **S3 Glacier Instant Retrieval**  | milliseconds   | Rarely accessed, but need fast access | ❄️⚡   |
| **S3 Glacier Flexible Retrieval** | minutes–hours  | Backups, archives                     | ❄️    |
| **S3 Glacier Deep Archive**       | 12–48 hours    | Long-term compliance (7–10 yrs)       | 🧊    |

---

### 🧠 Quick memory rule

* **Standard** → hot
* **IA** → warm
* **Glacier** → cold
* **Deep Archive** → frozen forever

---

## 🔐 S3 Policies & Access Control

### 🧾 1. Bucket Policy

* JSON policy attached to **bucket**
* Resource-based
* Cross-account access
* Public / private control

**Use when:**
👉 Grant access to many users or another AWS account

🧠 *Most common in exams*

---

### 👤 2. IAM Policy

* Attached to **users / roles**
* Identity-based
* Fine-grained permissions

**Use when:**
👉 Control what *this user/role* can do in S3

---

### 🏷️ 3. ACL (Access Control List)

* Legacy, object-level
* Limited control

**AWS recommendation:** ❌ avoid
🧠 *Exam answer often says “don’t use ACLs”*

---

### 🔐 4. S3 Access Points

* Named network access endpoints
* Simplifies complex bucket policies
* Can restrict by VPC

**Use when:**
👉 Large org, shared bucket, different teams

---

### 🌐 5. VPC Endpoint Policy (Gateway Endpoint)

* Controls S3 access **from VPC only**
* No internet required

**Use when:**
👉 Private subnets accessing S3 securely

---

### 🔑 6. Encryption Policies

| Type            | Managed by | Emoji |
| --------------- | ---------- | ----- |
| **SSE-S3**      | AWS        | 🔒    |
| **SSE-KMS**     | You (KMS)  | 🗝️   |
| **SSE-C**       | Customer   | 🧠    |
| **Client-side** | App        | 💻    |

🧠 *SSE-KMS = most secure + most exam answers*

---

## 🔄 Lifecycle Policy (VERY IMPORTANT)

Automates tier transitions & deletion

**Example**

```
Standard → Standard-IA → Glacier → Deep Archive → Delete
```

**Use when:**
👉 Cost optimization over time 💰

---

## 🚨 Common Exam Traps

* ❌ Glacier ≠ real-time access
* ❌ ACL is almost never correct
* ✅ Lifecycle policy for cost optimization
* ✅ Intelligent-Tiering when access pattern unknown
* ✅ VPC Endpoint + bucket policy for private access

