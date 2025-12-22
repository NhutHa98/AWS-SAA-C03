
## 🚀 Bảng so sánh chiến lược Migration (AWS 6R)

| Chiến lược        | Tên gọi khác      | Định nghĩa ngắn                     | Khi nào dùng      | Ưu điểm            | Nhược điểm           | Ví dụ                    |
| ----------------- | ----------------- | ----------------------------------- | ----------------- | ------------------ | -------------------- | ------------------------ |
| 🚚 **Rehost**     | Lift & Shift      | Bê nguyên hệ thống lên cloud        | Cần migrate nhanh | Nhanh, ít rủi ro   | Không tối ưu cloud   | VM → EC2                 |
| 🔧 **Replatform** | Lift-tinker-shift | Sửa **nhẹ** để dùng managed service | Muốn giảm ops     | Ít sửa code        | Chưa cloud-native    | EC2 DB → RDS             |
| 🧬 **Refactor**   | Re-architect      | Viết lại để cloud-native            | App chiến lược    | Tối ưu, scale tốt  | Tốn thời gian        | Monolith → Microservices |
| 📦 **Repurchase** | Drop & Shop       | Bỏ app cũ, dùng SaaS                | App không core    | Nhanh, ít vận hành | Mất custom           | CRM → SaaS               |
| 🛑 **Retire**     | Decommission      | Tắt app không cần nữa               | App không dùng    | Giảm chi phí       | Cần xác minh kỹ      | App nội bộ cũ            |
| ⏸️ **Retain**     | Revisit later     | Giữ nguyên on-prem                  | Chưa sẵn sàng     | Không rủi ro       | Không tận dụng cloud | App cần latency thấp     |

---

## 🧠 Nhớ nhanh theo **mức độ thay đổi**

```
Retain ─ Retire ─ Rehost ─ Replatform ─ Repurchase ─ Refactor
     (0%)                        →→→→→→→→→→→→→→→→ (100%)
```

* ⬅️ Trái: **ít thay đổi**
* ➡️ Phải: **cloud-native & tối ưu nhất**

---

## 🧰 Gắn chiến lược với dịch vụ AWS

| Chiến lược | AWS Service hay dùng          |
| ---------- | ----------------------------- |
| Rehost     | Application Migration Service |
| Replatform | RDS, ElastiCache              |
| Refactor   | ECS, EKS, Lambda              |
| Repurchase | SaaS (Salesforce, Workday)    |
| Retire     | Migration Hub                 |
| Retain     | Direct Connect                |

---

## ⚡ Câu hỏi hay gặp (exam & thực tế)

* **Muốn migrate nhanh nhất?** → Rehost
* **Giảm vận hành nhưng ít sửa code?** → Replatform
* **Muốn scale & tối ưu chi phí lâu dài?** → Refactor
* **App không còn giá trị?** → Retire
* **Chưa sẵn sàng migrate?** → Retain

