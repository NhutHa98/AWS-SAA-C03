

## 🖥️📱 Front-end Web & Mobile – Quick Compare

| Dịch vụ                         | Định nghĩa                                           | Use case thực tế                                                               | Ghi chú nhanh                                            |
| ------------------------------- | ---------------------------------------------------- | ------------------------------------------------------------------------------ | -------------------------------------------------------- |
| 🧩 **AWS Amplify**              | Nền tảng **full-stack cho front-end** (web & mobile) | - Host React / Next.js / Vue / Flutter<br>- Auth (Cognito), API, Storage nhanh | Opinionated, setup cực nhanh<br>🔥 Rất hợp dev front-end |
| 🔄 **AWS AppSync**              | **GraphQL managed service**                          | - Real-time app (chat, dashboard)<br>- Sync data đa nguồn                      | Subscriptions = real-time<br>Backend cho Amplify         |
| 📱 **AWS Device Farm**          | Test app trên **thiết bị thật & browser thật**       | - Test mobile app (iOS/Android)<br>- Cross-browser testing                     | Không phải runtime service<br>👉 dùng cho CI/CD          |
| 🗺️ **Amazon Location Service** | Dịch vụ **maps, geocoding, tracking**                | - Bản đồ cho web/mobile<br>- Track vị trí thiết bị                             | Thay Google Maps<br>Pricing rẻ hơn                       |

---

## 🔍 Phân loại theo use case (dễ nhớ)

### 🧱 Full-stack Front-end

* 🧩 **Amplify** → build & deploy app **siêu nhanh**

### 🔄 Data & Real-time

* **AppSync** → GraphQL + real-time (WebSocket)

### 🧪 Testing & QA

* **Device Farm** → test app trên **thiết bị thật**

### 🗺️ Location-based App

* **Amazon Location Service** → map + tracking + geofence

---

## ⚡ Gợi ý combo hay gặp

* **React / Next.js + Amplify + AppSync**
  → SaaS / Dashboard / Internal tool

* **Mobile app + AppSync + Location Service**
  → Delivery / Tracking / Ride-hailing style app

* **CI/CD + Device Farm**
  → Tránh bug “chạy được trên máy em” 😅


