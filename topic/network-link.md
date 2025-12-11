

# ✅ **1. AWS PrivateLink (Interface VPC Endpoint / Endpoint Service)**

### **Mô tả**

* Kết nối **private**, cấp độ **service-to-service**, không mở toàn subnet/VPC.
* Traffic **không đi qua Internet**, không cần VPN/peering.
* Chỉ expose **1 service** qua ENI.
* Một bên (provider) tạo **Endpoint Service**, bên kia tạo **Interface Endpoint**.

### **Use case**

* Truy cập **private API** của nhà cung cấp SaaS (Stripe, Snowflake, Datadog…).
* Truy cập microservice giữa 2 AWS account mà không mở toàn VPC.
* Kết nối private giữa VPC công ty và VPC đối tác.
* Tạo private SaaS marketplace offering.

### **Khi nào dùng**

✔ Khi yêu cầu chỉ truy cập đúng 1 service
✔ Khi muốn tránh mở rộng mạng
✔ Khi yêu cầu “traffic initiated only from client VPC”
✔ Khi đề thi nói **private, restrict to one service**

---

# ✅ **2. VPC Peering**

### **Mô tả**

* Kết nối **VPC-to-VPC**, kiểu flat network.
* Không dùng cho nhiều VPC trung gian (non-transitive).
* Route table cần thêm CIDR của nhau.

### **Use case**

* Kết nối internal giữa 2 VPC trong cùng account hoặc khác account.
* Microservice architecture nhưng **toàn VPC tin tưởng nhau**.
* Chia môi trường theo VPC: dev ↔ staging.

### **Khi nào dùng**

✔ Khi cần chia sẻ toàn bộ mạng
❌ Không phù hợp nếu phải restrict to one service
❌ Không phù hợp nếu chỉ được initiate từ một phía

---

# ✅ **3. AWS Transit Gateway (TGW) + VPC Attachment**

### **Mô tả**

* Hub-and-spoke network cho hàng trăm VPC.
* Hỗ trợ **inter-region**, **on-prem**, **VPN**, **DX**.

### **Use case**

* Tổ chức lớn với nhiều VPC (10–100+).
* Kết nối multi-region mesh.
* VPC ↔ on-prem VPN/Direct Connect.

### **Khi nào dùng**

✔ Enterprise scale
✔ Nhiều VPC muốn kết nối lẫn nhau
❌ Overkill nếu chỉ cần 1 service
❌ Không cung cấp service-level isolation

---

# ✅ **4. Site-to-Site VPN**

### **Mô tả**

* IPSec VPN qua public Internet.
* Thường kết nối on-prem ↔ AWS.

### **Use case**

* Hybrid cloud gateway cơ bản.
* Kết nối nhanh rẻ giữa doanh nghiệp ↔ AWS.
* Backup link cho Direct Connect.

### **Khi nào dùng**

✔ Hybrid
✔ Khi on-prem không có Direct Connect
❌ Không dùng cho VPC-to-VPC cùng AWS (dùng peering hoặc TGW tốt hơn)

---

# ✅ **5. AWS Direct Connect**

### **Mô tả**

* Kết nối vật lý, private, low latency giữa datacenter ↔ AWS.
* Có thể kết nối nhiều VPC qua Direct Connect Gateway.

### **Use case**

* Doanh nghiệp yêu cầu low latency và dedicated bandwidth.
* Truyền tải dữ liệu lớn.
* Kết nối multi-region.

### **Khi nào dùng**

✔ Enterprise, workload nặng
❌ Không dành cho VPC ↔ VPC
❌ Không dành cho mục tiêu service-level restriction

---

# ⚠️ **6. NAT Gateway**

Không phải private connectivity.
Traffic đi Internet → **không private → không dùng để kết nối VPC-to-VPC**.

---

# ⚠️ **7. Internet Gateway (IGW)**

Không phải loại kết nối private.

---

# ⚠️ **8. VPC Endpoint - Gateway Endpoint**

### **Mô tả**

* Chỉ dùng cho **S3** và **DynamoDB**.
* Không phù hợp cho service của provider.

---

# 📌 **So sánh nhanh (ghi nhớ thi)**

| Loại                | Direction     | Mức độ private   | Granularity                   | Use case                          |
| ------------------- | ------------- | ---------------- | ----------------------------- | --------------------------------- |
| **PrivateLink**     | One-way       | Very private     | **Service-level**             | Connect SaaS/provider service     |
| **VPC Peering**     | Bidirectional | Private          | **Network-level**             | Connect 2 trusted VPC             |
| **Transit Gateway** | Bidirectional | Private          | **Network-level (multi VPC)** | Enterprises w/ many VPC           |
| **VPN**             | Bidirectional | Encrypted        | Network-level                 | On-prem ↔ VPC                     |
| **Direct Connect**  | Bidirectional | Private physical | Network-level                 | Low latency, enterprise workloads |

