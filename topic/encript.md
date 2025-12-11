

# ✅ **1. Client-Side Encryption (mã hóa phía client)**

Ứng dụng hoặc SDK tự mã hóa **trước khi** gửi dữ liệu lên AWS.

### **Phương pháp**

* Tự mã hóa bằng AES-256, RSA… trước khi upload.
* AWS SDK cung cấp *Amazon S3 Encryption Client* (tự mã hóa local rồi mới upload).
* AWS không biết key của bạn.

### **Dùng khi**

* Tuân thủ yêu cầu rằng *AWS không được phép thấy dữ liệu*.

---

# ✅ **2. Server-Side Encryption (SSE)**

AWS mã hóa **sau khi nhận dữ liệu** và giải mã khi truy xuất.

---

# 🔶 **3 loại SSE chính (rất quan trọng trong tất cả kỳ thi AWS):**

## **SSE-S3**

* AWS S3 quản lý key.
* Không dùng KMS.
* **AES-256**
* Bật bằng header `"x-amz-server-side-encryption": "AES256"`.

✔️ Rẻ nhất
✔️ Không phải quản lý key → *ít vận hành nhất*

---

## **SSE-KMS**

* Dùng AWS KMS để quản lý key (CMK / KMS Key).
* Có thể audit qua CloudTrail.
* Có thể dùng **KMS multi-Region Key**.

✔️ Bảo mật cao hơn
✔️ Tích hợp KMS policies
❗ Tốn chi phí KMS ($0.03 per request)

---

## **SSE-C**

* Bạn tự quản lý key, gửi key theo header mỗi lần request.
* AWS không lưu key.

✔️ AWS không nắm key
❗ Yêu cầu gửi key mỗi lần → khó vận hành
❗ Chỉ S3 hỗ trợ

---

# 🔥 **3 kiểu encryption “at rest” (khi lưu trữ)**

## **1. EBS Encryption**

* SSE-KMS (bắt buộc dùng KMS key)
* Auto encrypt snapshots
* Replicate encrypted snapshots

## **2. RDS Encryption**

* SSE-KMS
* Bật khi tạo DB → không thay đổi được
* Snapshot giữ nguyên trạng thái encryption

## **3. DynamoDB Encryption**

* Dùng KMS key hoặc DynamoDB-managed key

---

# 🔥 **Encryption "in-transit" (khi truyền tải)**

* TLS/SSL
* HTTPS
* SSH
* VPN/IPsec
* PrivateLink + TLS

---

# 🔥 **Application Load Balancer / CloudFront**

* SSL/TLS termination
* ACM certificate
* SNI support

---

# 🔥 **S3 Encryption**

Tóm tắt:

| Loại    | Ai giữ key? | Chi phí                | Khi nào dùng?         |
| ------- | ----------- | ---------------------- | --------------------- |
| SSE-S3  | AWS         | Rẻ                     | ít vận hành           |
| SSE-KMS | KMS         | cao hơn                | audit + compliance    |
| SSE-C   | bạn         | free nhưng khó quản lý | dữ liệu siêu nhạy cảm |

---

# 🔥 **KMS Key Types**

* **AWS managed key** (không cần quản lý → ít overhead)
* **Customer managed key** (tự tạo, tự xoay vòng, tự đặt policy)
* **KMS multi-Region key**
* **Asymmetric keys (RSA/ECC)**
* **Symmetric keys (AES-256)** ← phổ biến nhất

---

# 🔥 **Các dịch vụ khác và cơ chế mã hóa**

## **SQS**

* SSE-KMS

## **SNS**

* SSE-KMS

## **CloudWatch Logs**

* SSE-KMS

## **Secrets Manager / Parameter Store**

* Tất cả đều dùng **KMS**

## **Lambda**

* Environment variables encrypted by KMS

## **EFS**

* Encryption at rest (KMS)
* TLS in transit

## **FSx (Windows, Lustre, NetApp)**

* Encryption at rest via KMS

## **Redshift**

* SSE-KMS

## **Glue**

* Encrypt job data + connections via KMS

## **Athena**

* Results in S3 → SSE-S3 or SSE-KMS

## **EMR**

* At rest: S3 server-side, local disk encryption KMS
* In transit: TLS

---

# 🔥 **Network encryption**

Không lưu dữ liệu nhưng vẫn là phần "encryption":

## **VPC**

* Encrypted traffic:

  * Site-to-Site VPN (IPSec)
  * Client VPN (OpenVPN)
  * AWS Direct Connect + MACsec (Layer 2 encryption)

---

# 🔥 **Summary map (dành cho thi SAA-C03)**

### **Encryption in AWS gồm 3 nhóm lớn:**

1. **In-transit**

   * TLS, IPSec, HTTPS

2. **At-rest**

   * SSE-S3
   * SSE-KMS
   * SSE-C

3. **Client-side encryption**

   * Tự mã hóa trước khi gửi

