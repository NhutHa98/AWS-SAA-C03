

## 🌍 Chặn truy cập theo Country – Bảng so sánh

| Dịch vụ                           | Chặn theo country | Áp dụng ở đâu                  | Linh hoạt rule | Dùng khi nào              | Ghi nhớ            |
| --------------------------------- | ----------------- | ------------------------------ | -------------- | ------------------------- | ------------------ |
| **AWS WAF** 🧱                    | ✅                 | CloudFront / ALB / API Gateway | ⭐⭐⭐⭐           | Web / API, cần nhiều rule | **Chuẩn nhất**     |
| **CloudFront Geo Restriction** 🌎 | ✅                 | CloudFront (Edge)              | ⭐⭐             | Static content            | Nhanh – đơn giản   |
| **Security Group** 🔐             | ❌                 | EC2 / ENI                      | ⭐              | Chặn IP cố định           | Không hiểu country |
| **Network ACL (NACL)** 🚧         | ❌                 | Subnet                         | ⭐              | Chặn CIDR rộng            | Stateless          |
| **AWS Shield** 🛡️                | ❌                 | L3/L4                          | ⭐              | DDoS                      | Không filter       |
| **GuardDuty** 🕵️                 | ❌                 | Monitoring                     | ⭐              | Phát hiện tấn công        | Không chặn         |
| **Inspector** 🔍                  | ❌                 | Scan                           | ⭐              | Tìm lỗ hổng               | Không runtime      |

---

## 🧠 Nhớ nhanh (1 dòng)

```
Country-based access → AWS WAF 🌍
```

---

## 🎯 Mẹo thi

* Thấy **country / geographic / region-based access**
  👉 **WAF**
* Thấy **static website + CloudFront**
  👉 Geo Restriction
* Thấy **IP / CIDR**
  👉 Security Group / NACL


