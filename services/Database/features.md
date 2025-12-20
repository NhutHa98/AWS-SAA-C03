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

### **DynamoDB Accelerator (DAX)**

**1️⃣ Định nghĩa**
DAX là **in-memory cache fully managed** cho DynamoDB, giúp **giảm latency từ milliseconds xuống microseconds** cho các read operation.

**2️⃣ Use case**

* Workload **read-heavy**, truy vấn lặp lại
* Ứng dụng cần **latency cực thấp** (real-time, gaming, leaderboard)
* Muốn cache DynamoDB **minh bạch**, không tự quản Redis

**3️⃣ Ghi chú**

* Chỉ hỗ trợ **read (Eventually Consistent)**
* Không cache write, write vẫn đi thẳng DynamoDB
* App phải dùng **DAX SDK/Client** (không hoàn toàn transparent)
