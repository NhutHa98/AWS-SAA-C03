

## 📊 Bảng so sánh Backup & DR Cross-Region (AWS)

| Phương án                                | Loại DB                 | Mục tiêu            | Realtime          | RPO                | RTO                  | Chi phí | Ưu điểm                       | Nhược điểm             | Khi nên dùng              |
| ---------------------------------------- | ----------------------- | ------------------- | ----------------- | ------------------ | -------------------- | ------- | ----------------------------- | ---------------------- | ------------------------- |
| **Manual Snapshot + Copy**               | RDS / Aurora            | Backup              | ❌                 | Vài giờ – vài ngày | Hàng chục phút – giờ | 💲      | Đơn giản, chủ động            | Dễ quên, không tự động | DB nhỏ, không critical    |
| **Automated Backup + Cross-Region Copy** | RDS / Aurora            | Backup              | ❌                 | Minutes – hours    | 30–90 phút           | 💲💲    | Tự động, ổn định              | Không DR realtime      | Hệ thống tiêu chuẩn       |
| **AWS Backup (Cross-Region)** ⭐          | RDS / Aurora / DynamoDB | Backup + Compliance | ❌                 | Minutes – hours    | 30–120 phút          | 💲💲    | Centralized, audit, retention | Không realtime         | Enterprise, nhiều account |
| **RDS Read Replica (Cross-Region)**      | RDS                     | DR + Read           | ⚠️ Near-real-time | Seconds – minutes  | 5–15 phút            | 💲💲    | DR nhanh, đọc được            | Lỗi logic vẫn sync     | App quan trọng            |
| **Aurora Cross-Region Replica**          | Aurora                  | DR                  | ⚠️                | < 1 phút           | 5–10 phút            | 💲💲    | Tối ưu cho Aurora             | Không instant failover | SaaS vừa–lớn              |
| **Aurora Global Database** ⭐⭐⭐           | Aurora                  | DR Critical         | ✅                 | < 1 giây           | < 1 phút             | 💲💲💲  | Failover cực nhanh            | Chi phí cao            | Mission-critical          |
| **DynamoDB Global Tables**               | DynamoDB                | DR + Active-Active  | ✅                 | ~0                 | Seconds              | 💲💲💲  | Multi-region native           | Conflict handling      | Global app                |
| **Export DB → S3 + Replication**         | All                     | Long-term backup    | ❌                 | 24h+               | Giờ – ngày           | 💲      | Lưu trữ rẻ                    | Restore chậm           | Compliance / archive      |

---

## 🧠 Hiểu nhanh RPO & RTO trong bảng

* **RPO (Recovery Point Objective)**
  → *Chấp nhận mất bao nhiêu dữ liệu*

  * Snapshot: mất dữ liệu từ lần backup gần nhất
  * Replica: mất vài giây–phút
  * Global DB: gần như 0

* **RTO (Recovery Time Objective)**
  → *Bao lâu hệ thống chạy lại*

  * Snapshot restore: lâu
  * Replica promote: nhanh
  * Global DB: gần như instant

---

## 🏗️ Kiến trúc khuyến nghị theo mức độ quan trọng

### 🔹 Non-critical system

```
RDS
 └─ Automated Backup + Cross-Region Copy
```

RPO: giờ
RTO: ~1h

---

### 🔹 Business-critical system

```
RDS
 ├─ Cross-Region Read Replica (DR)
 └─ AWS Backup (Compliance)
```

RPO: phút
RTO: 5–15 phút

---

### 🔹 Mission-critical / Fintech / SaaS lớn

```
Aurora Global Database
 └─ AWS Backup (Snapshot cold backup)
```

RPO: < 1s
RTO: < 1 phút

---

## ✅ Kết luận nhanh

* **Backup ≠ Disaster Recovery**
* Snapshot = **data safety**
* Replica / Global DB = **service availability**
* Hệ thống tốt thường dùng **CẢ HAI**

