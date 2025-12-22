
## 🚚 Migration & Transfer – AWS Services Comparison

| Dịch vụ                                         | Định nghĩa                                               | Use case thực tế                                       | Ghi chú nhanh                                              | Tags                                  |
| ----------------------------------------------- | -------------------------------------------------------- | ------------------------------------------------------ | ---------------------------------------------------------- | ------------------------------------- |
| 🧭 **AWS Migration Hub**                        | Trung tâm theo dõi & quản lý toàn bộ quá trình migration | Theo dõi tiến độ migrate nhiều app/db từ on-prem → AWS | ❌ Không migrate dữ liệu<br>✅ Chỉ **tracking & visibility** | `#tracking` `#migration-dashboard`    |
| 🖥️ **AWS Application Migration Service (MGN)** | Lift & Shift server lên AWS                              | Migrate VM/physical server → EC2                       | Block-level replication<br>Downtime thấp                   | `#lift-and-shift` `#server-migration` |
| 🔍 **Application Discovery Service**            | Thu thập thông tin hệ thống on-prem                      | Phân tích dependency trước khi migrate                 | Dùng trước MGN/DMS<br>Agent & agentless                    | `#discovery` `#assessment`            |
| 🛢️ **AWS Database Migration Service (DMS)**    | Migrate database với downtime thấp                       | Oracle → Aurora, MySQL → DynamoDB                      | Support CDC (near-zero downtime)                           | `#database-migration` `#cdc`          |
| 📂 **AWS Transfer Family**                      | SFTP/FTPS/FTP vào AWS                                    | Cho đối tác upload file vào S3/EFS                     | Managed SFTP server                                        | `#file-transfer` `#sftp`              |
| ❄️ **AWS Snow Family**                          | Thiết bị vật lý chuyển data lớn                          | Migrate PB data khi mạng chậm                          | Snowcone / Snowball / Snowmobile                           | `#offline-transfer` `#petabyte`       |
| 🔄 **AWS DataSync**                             | Đồng bộ dữ liệu tốc độ cao                               | On-prem NAS → S3/EFS                                   | Incremental, encrypted                                     | `#sync` `#hybrid`                     |
| 🔧 **AWS Transform**                            | Tự động refactor workload                                | Modernize Java/.NET app                                | Thường dùng kèm modernization                              | `#refactor` `#modernization`          |
| 🏦 **AWS Mainframe Modernization**              | Hiện đại hóa mainframe                                   | COBOL → microservices                                  | Rất enterprise & costly                                    | `#mainframe` `#legacy`                |
| ☁️ **Amazon Elastic VMware Service**            | Chạy VMware native trên AWS                              | Lift VMware mà không đổi kiến trúc                     | Không cần convert VM                                       | `#vmware` `#hybrid-cloud`             |

---

## 🧠 Nhóm nhanh theo **mục tiêu Migration**

### 🔁 Lift & Shift

* 🖥️ Application Migration Service
* ☁️ Elastic VMware Service

### 🔍 Discover & Assess

* 🔍 Application Discovery Service
* 🧭 Migration Hub

### 🛢️ Database

* 🛢️ Database Migration Service (DMS)

### 📦 Data Transfer

* 🔄 DataSync (online)
* ❄️ Snow Family (offline, siêu lớn)
* 📂 Transfer Family (SFTP/FTP)

### 🧬 Modernization

* 🔧 AWS Transform
* 🏦 Mainframe Modernization

---

## ⚡ Câu hỏi hay gặp trong exam / thực tế

* **Theo dõi toàn bộ migration?** → 🧭 Migration Hub
* **Lift & shift nhanh, downtime thấp?** → 🖥️ MGN
* **CDC database?** → 🛢️ DMS
* **Migrate 5PB, mạng yếu?** → ❄️ Snowball
* **Đối tác cần SFTP upload file?** → 📂 Transfer Family
* **Giữ nguyên VMware?** → ☁️ Elastic VMware Service


---
# **Chi tiết** 

# 🚚 Migration & Transfer – Chi tiết từng dịch vụ (AWS)

---

## 🧭 AWS Migration Hub

**👉 Vai trò:** *“Bảng điều khiển trung tâm” cho mọi hoạt động migration*

### 🔹 Định nghĩa

Migration Hub giúp **theo dõi, quản lý và visualize** tiến độ migrate ứng dụng, server, database từ on-prem / cloud khác → AWS.

### 🔹 Use case

* Theo dõi **nhiều team migrate song song**
* Biết app nào đang *discover → migrate → complete*
* Tổng hợp dữ liệu từ MGN, DMS, Discovery Service

### 🔹 Thành phần / dịch vụ con

* **Migration Hub Orchestrator** – workflow migration (runbook)
* **Integration** với:

  * Application Migration Service
  * Database Migration Service
  * Application Discovery Service

### 🔹 Ghi chú

* ❌ Không migrate data
* ✅ Chỉ **tracking + orchestration**
* Rất hay dùng trong enterprise migration

**Tags:** `#dashboard` `#orchestration` `#visibility`

---

## 🖥️ AWS Application Migration Service (MGN)

**👉 Vai trò:** *Lift & Shift server*

### 🔹 Định nghĩa

Migrate **VM hoặc physical server** sang EC2 bằng **block-level replication**, downtime rất thấp.

### 🔹 Use case

* Lift & shift app legacy
* Migrate VMware / Hyper-V / bare metal
* Không muốn refactor ngay

### 🔹 Thành phần / dịch vụ con

* **Replication Agent** (cài on-prem)
* **Staging Area subnet**
* **EC2 Launch Templates**
* **Test & Cutover instances**

### 🔹 Ghi chú

* Không đổi OS / app
* Phù hợp giai đoạn **rehost**
* Thường dùng cùng Migration Hub

**Tags:** `#lift-and-shift` `#server-migration`

---

## 🔍 AWS Application Discovery Service

**👉 Vai trò:** *Hiểu hệ thống trước khi migrate*

### 🔹 Định nghĩa

Thu thập thông tin về:

* CPU, RAM, disk
* Network traffic
* Dependency giữa các server/app

### 🔹 Use case

* Vẽ dependency map
* Xác định **migration waves**
* Input cho MGN & DMS

### 🔹 Thành phần / dịch vụ con

* **Agent-based Discovery**
* **Agentless Discovery**
* **Discovery Connector**
* **Export CSV / integrate Migration Hub**

### 🔹 Ghi chú

* Không migrate
* Rất hay bị nhầm với Migration Hub
* Dùng **trước** migration

**Tags:** `#discovery` `#assessment` `#dependency`

---

## 🛢️ AWS Database Migration Service (DMS)

**👉 Vai trò:** *Migrate database, downtime thấp*

### 🔹 Định nghĩa

Migrate database **homogeneous / heterogeneous** với khả năng **CDC (Change Data Capture)**.

### 🔹 Use case

* Oracle → Aurora
* MySQL → PostgreSQL
* On-prem → RDS / DynamoDB

### 🔹 Thành phần / dịch vụ con

* **Replication Instance**
* **Source Endpoint**
* **Target Endpoint**
* **Migration Tasks**
* **CDC mode**

### 🔹 Ghi chú

* Không convert schema → cần **AWS SCT**
* Near-zero downtime
* Một trong dịch vụ hay ra exam nhất

**Tags:** `#database-migration` `#cdc`

---

## 📂 AWS Transfer Family

**👉 Vai trò:** *Managed SFTP/FTP server*

### 🔹 Định nghĩa

Cung cấp **SFTP, FTPS, FTP** endpoint để truyền file trực tiếp vào AWS storage.

### 🔹 Use case

* Đối tác upload file
* Legacy system dùng SFTP
* Data exchange automation

### 🔹 Thành phần / dịch vụ con

* **Transfer for SFTP**
* **Transfer for FTPS**
* **Transfer for FTP**
* Backend:

  * Amazon S3
  * Amazon EFS
* Authentication:

  * Service-managed
  * AWS Directory Service
  * Custom (Lambda)

### 🔹 Ghi chú

* Không cần tự dựng SFTP server
* Pay-per-use
* Rất phổ biến trong enterprise

**Tags:** `#file-transfer` `#sftp`

---

## ❄️ AWS Snow Family

**👉 Vai trò:** *Chuyển data khi network không đủ*

### 🔹 Định nghĩa

Thiết bị vật lý để **transfer dữ liệu offline** với dung lượng cực lớn.

### 🔹 Use case

* Migrate hàng trăm TB – PB
* Data center ở nơi mạng yếu
* Disaster recovery

### 🔹 Thành phần / dịch vụ con

* **Snowcone** – nhỏ, edge
* **Snowball Edge** – phổ biến
* **Snowmobile** – exabyte scale
* **Snow Family Ops Hub**

### 🔹 Ghi chú

* Dữ liệu được **encrypt**
* Shipping vật lý
* Không dùng cho sync liên tục

**Tags:** `#offline-transfer` `#big-data`

---

## 🔄 AWS DataSync

**👉 Vai trò:** *Sync dữ liệu online, tốc độ cao*

### 🔹 Định nghĩa

Dịch vụ **automated, incremental** để sync data từ on-prem / cloud → AWS.

### 🔹 Use case

* NAS → S3
* EFS ↔ EFS
* Hybrid workload

### 🔹 Thành phần / dịch vụ con

* **DataSync Agent**
* **Task**
* **Location (source/target)**
* Targets:

  * S3
  * EFS
  * FSx

### 🔹 Ghi chú

* Thay thế rsync
* Tối ưu network
* Không cần custom script

**Tags:** `#sync` `#hybrid`

---

## 🔧 AWS Transform

**👉 Vai trò:** *Refactor & modernize*

### 🔹 Định nghĩa

Giúp **tự động phân tích và refactor code** khi modernize application.

### 🔹 Use case

* Java monolith → cloud-ready
* .NET legacy → container
* Chuẩn bị cho microservices

### 🔹 Thành phần / dịch vụ con

* Code analysis
* Refactoring recommendations
* Integration với modernization tools

### 🔹 Ghi chú

* Không phải lift & shift
* Dùng khi đã quyết định **refactor**

**Tags:** `#refactor` `#modernization`

---

## 🏦 AWS Mainframe Modernization

**👉 Vai trò:** *Thoát khỏi mainframe*

### 🔹 Định nghĩa

Modernize workload mainframe (COBOL, PL/I) lên AWS.

### 🔹 Use case

* Giảm chi phí mainframe
* Từng bước chuyển sang cloud-native

### 🔹 Thành phần / dịch vụ con

* **Replatform approach**
* **Refactor approach**
* **Managed runtime**
* **Blu Age / Micro Focus integration**

### 🔹 Ghi chú

* Rất enterprise
* Chi phí & planning lớn
* Dùng trong roadmap dài hạn

**Tags:** `#mainframe` `#legacy`

---

## ☁️ Amazon Elastic VMware Service

**👉 Vai trò:** *VMware native trên AWS*

### 🔹 Định nghĩa

Chạy **VMware Cloud Foundation** trực tiếp trên hạ tầng AWS.

### 🔹 Use case

* Không muốn đổi kiến trúc
* Hybrid cloud VMware
* Migration nhanh

### 🔹 Thành phần / dịch vụ con

* vSphere
* vSAN
* NSX
* VMware HCX

### 🔹 Ghi chú

* Không cần convert VM
* Chi phí cao
* Rất hợp phase trung gian

**Tags:** `#vmware` `#hybrid`

---

👉 Nếu bạn muốn bước tiếp theo, mình có thể:

* 📊 **So sánh dịch vụ nào dùng ở phase nào (Assess → Migrate → Modernize)**
* 🧠 **Mindmap dạng text / markdown**
* 📝 **One-page summary cho thi SAA / SAP**

Bạn muốn đi hướng nào tiếp?
