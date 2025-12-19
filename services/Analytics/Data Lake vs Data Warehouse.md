

## 🆚 Data Lake vs Data Warehouse

| Tiêu chí          | 🌊 **Data Lake**               | 🏢 **Data Warehouse**                    |
| ----------------- | ------------------------------ | ---------------------------------------- |
| 🎯 Mục đích       | Lưu **mọi loại dữ liệu**       | Phân tích **business data đã chuẩn hóa** |
| 📦 Loại dữ liệu   | Structured, Semi, Unstructured | Chủ yếu Structured                       |
| 🕒 Schema         | **Schema-on-read**             | **Schema-on-write**                      |
| 💾 Storage        | Object storage (S3)            | Columnar storage                         |
| ⚡ Hiệu năng query | Trung bình (phụ thuộc engine)  | Rất cao, tối ưu BI                       |
| 💰 Chi phí        | Rẻ, scale lớn                  | Đắt hơn                                  |
| 👥 Người dùng     | Data engineer, data scientist  | Business analyst                         |
| 🔄 Dữ liệu        | Raw → Clean → Curated          | Clean & Aggregated                       |
| 🧠 ML / AI        | Rất phù hợp                    | Hạn chế                                  |
| 🔐 Governance     | Cần tool bổ sung               | Built-in chặt chẽ                        |

---

## 🧩 Mapping sang AWS (rất hay ra đề thi)

### 🌊 Data Lake (AWS)

* **S3** → lưu raw data
* **AWS Glue** → ETL + Data Catalog
* **Lake Formation** → security & governance
* **Athena / EMR / Spark** → query & processing

👉 Dùng khi:

* Big data
* Log, clickstream, IoT
* ML / AI
* Chưa biết trước schema

---

### 🏢 Data Warehouse (AWS)

* **Amazon Redshift**
* **QuickSight** (BI)
* **Redshift Spectrum** (query S3)

👉 Dùng khi:

* BI, reporting
* KPI, dashboard
* Query nhanh, join phức tạp
* Data đã chuẩn hóa

---

## 🔥 So sánh nhanh bằng ví dụ thực tế

| Tình huống                       | Chọn              |
| -------------------------------- | ----------------- |
| Log từ web/app, format lung tung | 🌊 Data Lake      |
| Báo cáo doanh thu hàng ngày      | 🏢 Data Warehouse |
| Train ML model                   | 🌊 Data Lake      |
| CEO cần dashboard real-time-ish  | 🏢 Data Warehouse |
| Lưu data “để đó, sau tính”       | 🌊 Data Lake      |

---

## 🤝 Mô hình phổ biến hiện nay: **Lakehouse**

> Kết hợp **Data Lake + Data Warehouse**

### Trên AWS:

* **S3 (Data Lake)**
* **Glue + Lake Formation**
* **Athena / Redshift Spectrum**
* **QuickSight**

👉 Vừa rẻ, vừa linh hoạt, vẫn BI ngon.

---

## 🧠 3 câu nhớ để đi thi / đi phỏng vấn

1. 🌊 **Data Lake** = lưu *tất cả*, rẻ, linh hoạt, schema-on-read
2. 🏢 **Data Warehouse** = query *siêu nhanh*, BI, schema-on-write
3. 🤝 **Lakehouse** = best of both worlds

