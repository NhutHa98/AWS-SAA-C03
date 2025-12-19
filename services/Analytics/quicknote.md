
## 📊 Query, BI & Data Warehouse

| Dịch vụ                   | Định nghĩa                               | Use case chính                    | Ghi chú                                   |
| ------------------------- | ---------------------------------------- | --------------------------------- | ----------------------------------------- |
| 🟦 **Athena**             | Query SQL trực tiếp trên S3 (serverless) | Ad-hoc query log, data lake       | Không cần server, trả tiền theo data scan |
| 🟥 **Amazon Redshift**    | Data Warehouse hiệu năng cao             | BI, reporting lớn, join phức tạp  | Có RA3, Spectrum query S3                 |
| 🟪 **QuickSight**         | BI & Data Visualization                  | Dashboard, report cho business    | SPICE engine, tích hợp Athena/Redshift    |
| 🟪 **Amazon Quick Suite** | Bộ công cụ BI (QuickSight + add-ons)     | End-to-end analytics cho business | Không phải service riêng biệt             |

---

## 🔍 Search & Log Analytics

| Dịch vụ                          | Định nghĩa                            | Use case chính                       | Ghi chú                              |
| -------------------------------- | ------------------------------------- | ------------------------------------ | ------------------------------------ |
| 🔎 **CloudSearch**               | Managed search engine (legacy)        | Search đơn giản cho app              | Ít dùng, thường thay bằng OpenSearch |
| 🔎 **Amazon OpenSearch Service** | Search & log analytics (Elastic-like) | Log, full-text search, observability | Có OpenSearch Dashboards             |

---

## 🌊 Streaming, Real-time Analytics

| Dịch vụ                     | Định nghĩa                         | Use case chính                 | Ghi chú                               |
| --------------------------- | ---------------------------------- | ------------------------------ | ------------------------------------- |
| ⚡ **Kinesis**               | Streaming data platform            | Clickstream, IoT, log realtime | Gồm Data Streams, Firehose, Analytics |
| 🚀 **Amazon Data Firehose** | Streaming → S3/Redshift/OpenSearch | Ingest data realtime           | Fully managed, near-real-time         |
| 🟠 **MSK (Kafka)**          | Managed Apache Kafka               | Event streaming quy mô lớn     | Phù hợp hệ sinh thái Kafka            |
| 🧠 **Managed Apache Flink** | Stream processing real-time        | Window, aggregation, CEP       | Thay Kinesis Data Analytics cũ        |

---

## 🏗️ Data Lake, ETL & Data Preparation

| Dịch vụ                   | Định nghĩa                    | Use case chính             | Ghi chú                        |
| ------------------------- | ----------------------------- | -------------------------- | ------------------------------ |
| 🧩 **AWS Glue**           | ETL serverless + Data Catalog | Build data pipeline        | Spark-based                    |
| 🧼 **AWS Glue DataBrew**  | No-code data prep             | Clean, normalize data      | Dành cho data analyst          |
| 🟢 **AWS Lake Formation** | Quản trị & bảo mật Data Lake  | Centralized access control | IAM + fine-grained permissions |
| 🧭 **Amazon DataZone**    | Data catalog & governance     | Discover, share data       | Kiểu “data marketplace nội bộ” |

---

## 🏔️ Big Data Processing

| Dịch vụ                 | Định nghĩa             | Use case chính            | Ghi chú                       |
| ----------------------- | ---------------------- | ------------------------- | ----------------------------- |
| 🐘 **EMR**              | Managed Hadoop/Spark   | Batch processing, ML prep | Flexible nhưng cần tuning     |
| 🧠 **Amazon SageMaker** | ML platform end-to-end | Train, deploy ML models   | Không chỉ analytics, thiên ML |

---

## 🤝 Data Sharing, Collaboration & Privacy

| Dịch vụ                      | Định nghĩa             | Use case chính          | Ghi chú                        |
| ---------------------------- | ---------------------- | ----------------------- | ------------------------------ |
| 🔄 **AWS Data Exchange**     | Marketplace dữ liệu    | Mua/bán data            | Public & private datasets      |
| 🛡️ **AWS Clean Rooms**      | Phân tích data bảo mật | Cross-company analytics | Không lộ raw data              |
| 🧬 **AWS Entity Resolution** | Match & dedupe entity  | Customer 360            | Không cần build logic phức tạp |

---

## 🧮 Financial & Industry-specific Analytics

| Dịch vụ                | Định nghĩa              | Use case chính             | Ghi chú                       |
| ---------------------- | ----------------------- | -------------------------- | ----------------------------- |
| 💰 **Amazon FinSpace** | Analytics cho tài chính | Time-series, risk analysis | Tối ưu cho financial services |

---

## 🧠 Tóm tắt “chọn nhanh cho đúng”

* ❓ **Query nhanh trên S3** → Athena
* 📈 **BI & Dashboard** → QuickSight + Athena/Redshift
* 🌊 **Streaming real-time** → Kinesis / MSK + Flink
* 🏗️ **ETL & Data Lake** → Glue + Lake Formation
* 🔍 **Log & Search** → OpenSearch
* 🧠 **ML & Advanced analytics** → SageMaker
* 🤝 **Chia sẻ data an toàn** → Clean Rooms / DataZone
