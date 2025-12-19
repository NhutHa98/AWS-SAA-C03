Ok! Mình sẽ làm phiên bản **trực quan hơn**, dùng **emoji cho category + mục tiêu + ghi chú**, highlight các keyword quan trọng, để đọc nhanh kiểu cheat sheet:

| 🌐 Service                          | 🔹 **Định nghĩa**                          | 🛠️ **Use Case**                               | 📝 **Ghi chú**                                       |
| ----------------------------------- | ------------------------------------------ | ---------------------------------------------- | ---------------------------------------------------- |
| **VPC**                             | Mạng ảo riêng trên AWS                     | ✅ Tách biệt mạng, triển khai EC2/RDS/Lambda    | Cơ sở hạ tầng mạng của hầu hết AWS services          |
| **CloudFront**                      | CDN (Content Delivery Network)             | ⚡ Tăng tốc website & file tĩnh/động            | Bảo vệ DDoS, tích hợp S3/API Gateway/ALB             |
| **API Gateway**                     | Quản lý API HTTP/REST/WebSocket            | 📡 Serverless backend hoặc proxy API           | Hỗ trợ throttling, auth, caching                     |
| **Direct Connect**                  | Kết nối riêng từ on-premise → AWS          | 🔗 Kết nối ổn định, băng thông cao             | Bypass internet công cộng, hybrid cloud              |
| **AWS App Mesh**                    | Service mesh quản lý microservices traffic | 🌀 Giám sát, routing, bảo mật microservices    | Dùng với ECS/EKS/EC2                                 |
| **Global Accelerator**              | Tối ưu routing traffic toàn cầu            | 🌍 Cải thiện performance & availability global | Traffic qua AWS edge location                        |
| **Route 53**                        | DNS service & domain management            | 🌐 Domain routing, health check, failover      | Hỗ trợ latency/geolocation/failover routing policies |
| **AWS Data Transfer Terminal**      | Gateway cho dữ liệu lớn                    | 📦 Chuyển dữ liệu on-premise → AWS             | Dùng khi băng thông internet hạn chế                 |
| **Route 53 Global Resolver**        | DNS resolver toàn cầu                      | 🌎 Hybrid cloud, private DNS resolution        | Hỗ trợ VPC-to-VPC & on-premise DNS queries           |
| **AWS Cloud Map**                   | Service discovery                          | 🔍 Microservices tìm nhau bằng tên/IP          | Hỗ trợ ECS, Lambda, EC2                              |
| **RTB Fabric**                      | Real-time Bidding network fabric           | 🎯 Quảng cáo programmatic, tối ưu latency      | Chủ yếu dùng trong ad-tech                           |
| **Application Recovery Controller** | Giám sát & orchestrate recovery            | 🚑 Disaster recovery cho critical app          | Kết hợp Route 53 failover & CloudWatch               |

✅ **Tip trực quan:**

* 🌐 Networking / Internet
* ⚡ Performance / CDN
* 🔗 Kết nối trực tiếp / private
* 🌀 Microservices / routing
* 🌍 / 🌎 / 🚑 Global / DR / high availability

---

Mình có thể làm thêm **phiên bản “color-coded” kiểu infographic mini**, chỉ nhìn bảng là nhớ chức năng luôn, cực nhanh cho học hoặc thuyết trình.

Bạn có muốn mình làm phiên bản đó luôn không?
