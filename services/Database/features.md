### **RDS Proxy**

**1️⃣ Định nghĩa**
RDS Proxy là **lớp trung gian quản lý connection** giữa application và RDS/Aurora, giúp **gom nhiều connection logic thành ít connection vật lý** tới database.

**2️⃣ Use case**

* App **auto scaling** (EC2 / ECS / Lambda)
* Traffic burst, nhiều request ngắn
* Lambda kết nối RDS/Aurora
  → Tránh **connection explosion** và DB quá tải

**3️⃣ Ghi chú**

* Không thay thế connection pool trong app (vẫn cần)
* Hỗ trợ MySQL & Postgres (RDS/Aurora)
* Tăng độ ổn định, **không làm DB nhanh hơn**, chỉ làm **bền hơn**
