# AWS & Networking Keywords Reference
*Tài liệu tham khảo từ khóa AWS & Mạng*

---

## 1. AWS Core Services
*Các dịch vụ cốt lõi AWS*

### 1.1 Compute Services
*Dịch vụ tính toán*

**1.1.1 EC2 (Elastic Compute Cloud)**
- EN: Virtual servers in the cloud with scalable computing capacity
- VN: Máy chủ ảo trên cloud với khả năng mở rộng tính toán

**1.1.2 Lambda**
- EN: Serverless compute service that runs code without managing servers
- VN: Dịch vụ tính toán không máy chủ chạy code mà không cần quản lý server

**1.1.3 ECS (Elastic Container Service)**
- EN: Container orchestration service for Docker containers
- VN: Dịch vụ điều phối container cho Docker containers

**1.1.4 EKS (Elastic Kubernetes Service)**
- EN: Managed Kubernetes service for container orchestration
- VN: Dịch vụ Kubernetes được quản lý cho điều phối container

### 1.2 Storage Services
*Dịch vụ lưu trữ*

**1.2.1 S3 (Simple Storage Service)**
- EN: Object storage service with unlimited scalability
- VN: Dịch vụ lưu trữ đối tượng với khả năng mở rộng không giới hạn

**1.2.2 EBS (Elastic Block Store)**
- EN: Block-level storage volumes for EC2 instances
- VN: Ổ đĩa lưu trữ khối cho các EC2 instances

**1.2.3 EFS (Elastic File System)**
- EN: Fully managed NFS file system for EC2
- VN: Hệ thống file NFS được quản lý hoàn toàn cho EC2

**1.2.4 Glacier**
- EN: Low-cost archive storage for long-term backup
- VN: Lưu trữ lưu trữ chi phí thấp cho sao lưu dài hạn

**1.2.5 Storage Gateway**
- EN: Hybrid cloud storage service connecting on-premises to AWS
- VN: Dịch vụ lưu trữ hybrid cloud kết nối on-premises với AWS

### 1.3 Database Services
*Dịch vụ cơ sở dữ liệu*

**1.3.1 RDS (Relational Database Service)**
- EN: Managed relational database service (MySQL, PostgreSQL, etc.)
- VN: Dịch vụ cơ sở dữ liệu quan hệ được quản lý

**1.3.2 DynamoDB**
- EN: NoSQL database service with single-digit millisecond performance
- VN: Dịch vụ cơ sở dữ liệu NoSQL với hiệu suất millisecond

**1.3.3 Aurora**
- EN: MySQL and PostgreSQL compatible relational database
- VN: Cơ sở dữ liệu quan hệ tương thích MySQL và PostgreSQL

**1.3.4 ElastiCache**
- EN: In-memory caching service (Redis/Memcached)
- VN: Dịch vụ cache trong bộ nhớ

**1.3.5 Redshift**
- EN: Data warehouse service for analytics
- VN: Dịch vụ kho dữ liệu cho phân tích

---

## 2. AWS Networking Services
*Dịch vụ mạng AWS*

### 2.1 Core Networking
*Mạng cốt lõi*

**2.1.1 VPC (Virtual Private Cloud)**
- EN: Isolated virtual network within AWS cloud
- VN: Mạng ảo biệt lập trong AWS cloud

**2.1.2 Route 53**
- EN: Scalable DNS web service and domain registration
- VN: Dịch vụ DNS có thể mở rộng và đăng ký tên miền

**2.1.3 CloudFront**
- EN: Content Delivery Network (CDN) for fast content delivery
- VN: Mạng phân phối nội dung để phân phối nội dung nhanh

**2.1.4 ELB (Elastic Load Balancer)**
- EN: Distributes incoming traffic across multiple targets
- VN: Phân phối lưu lượng truy cập đến nhiều mục tiêu

**2.1.5 API Gateway**
- EN: Service for creating, publishing, and managing APIs
- VN: Dịch vụ tạo, xuất bản và quản lý APIs

### 2.2 VPC Components
*Thành phần VPC*

**2.2.1 Subnet**
- EN: Range of IP addresses in VPC, can be public or private
- VN: Dải địa chỉ IP trong VPC, có thể là công khai hoặc riêng tư

**2.2.2 Internet Gateway (IGW)**
- EN: Allows communication between VPC and internet
- VN: Cho phép giao tiếp giữa VPC và internet

**2.2.3 NAT Gateway**
- EN: Enables private subnet instances to access internet
- VN: Cho phép các instance trong subnet riêng truy cập internet

**2.2.4 Route Table**
- EN: Contains rules (routes) that determine network traffic direction
- VN: Chứa các quy tắc xác định hướng lưu lượng mạng

**2.2.5 Security Group**
- EN: Virtual firewall controlling inbound/outbound traffic
- VN: Tường lửa ảo kiểm soát lưu lượng vào/ra

**2.2.6 NACL (Network Access Control List)**
- EN: Subnet-level firewall with allow/deny rules
- VN: Tường lửa cấp subnet với quy tắc cho phép/từ chối

### 2.3 Connectivity Services
*Dịch vụ kết nối*

**2.3.1 VPN Gateway**
- EN: Connects on-premises networks to VPC via VPN
- VN: Kết nối mạng on-premises với VPC qua VPN

**2.3.2 Direct Connect**
- EN: Dedicated network connection from premises to AWS
- VN: Kết nối mạng chuyên dụng từ cơ sở hạ tầng đến AWS

**2.3.3 Transit Gateway**
- EN: Network hub connecting VPCs and on-premises networks
- VN: Hub mạng kết nối các VPC và mạng on-premises

**2.3.4 VPC Peering**
- EN: Network connection between two VPCs
- VN: Kết nối mạng giữa hai VPC

---

## 3. AWS Security & Identity
*Bảo mật & Danh tính AWS*

### 3.1 Identity Services
*Dịch vụ danh tính*

**3.1.1 IAM (Identity and Access Management)**
- EN: Service for managing users, groups, and permissions
- VN: Dịch vụ quản lý người dùng, nhóm và quyền

**3.1.2 Cognito**
- EN: User identity and authentication service for web/mobile apps
- VN: Dịch vụ danh tính và xác thực người dùng cho ứng dụng web/mobile

**3.1.3 SSO (Single Sign-On)**
- EN: Centrally manage access to multiple AWS accounts
- VN: Quản lý truy cập tập trung đến nhiều tài khoản AWS

### 3.2 Security Services
*Dịch vụ bảo mật*

**3.2.1 WAF (Web Application Firewall)**
- EN: Protects web applications from common exploits
- VN: Bảo vệ ứng dụng web khỏi các cuộc tấn công phổ biến

**3.2.2 Shield**
- EN: DDoS protection service for AWS applications
- VN: Dịch vụ bảo vệ DDoS cho ứng dụng AWS

**3.2.3 GuardDuty**
- EN: Threat detection service using machine learning
- VN: Dịch vụ phát hiện mối đe dọa sử dụng machine learning

**3.2.4 KMS (Key Management Service)**
- EN: Managed service for creating and controlling encryption keys
- VN: Dịch vụ được quản lý để tạo và kiểm soát khóa mã hóa

---

## 4. AWS Management & Monitoring
*Quản lý & Giám sát AWS*

### 4.1 Monitoring Services
*Dịch vụ giám sát*

**4.1.1 CloudWatch**
- EN: Monitoring service for AWS resources and applications
- VN: Dịch vụ giám sát cho tài nguyên và ứng dụng AWS

**4.1.2 CloudTrail**
- EN: Service for logging and monitoring API calls
- VN: Dịch vụ ghi log và giám sát các lời gọi API

**4.1.3 Config**
- EN: Service for assessing and auditing AWS resource configurations
- VN: Dịch vụ đánh giá và kiểm toán cấu hình tài nguyên AWS

### 4.2 Deployment Services
*Dịch vụ triển khai*

**4.2.1 CloudFormation**
- EN: Infrastructure as Code service using templates
- VN: Dịch vụ Infrastructure as Code sử dụng templates

**4.2.2 CodeDeploy**
- EN: Automated application deployment service
- VN: Dịch vụ triển khai ứng dụng tự động

**4.2.3 Elastic Beanstalk**
- EN: Platform service for deploying web applications
- VN: Dịch vụ nền tảng để triển khai ứng dụng web

---

## 5. Networking Fundamentals
*Kiến thức mạng cơ bản*

### 5.1 Network Protocols
*Giao thức mạng*

**5.1.1 TCP (Transmission Control Protocol)**
- EN: Reliable, connection-oriented protocol for data transmission
- VN: Giao thức kết nối đáng tin cậy để truyền dữ liệu

**5.1.2 UDP (User Datagram Protocol)**
- EN: Fast, connectionless protocol for data transmission
- VN: Giao thức không kết nối nhanh để truyền dữ liệu

**5.1.3 HTTP/HTTPS**
- EN: Web protocols for transferring web content (secure version)
- VN: Giao thức web để truyền nội dung web (phiên bản bảo mật)

**5.1.4 DNS (Domain Name System)**
- EN: System that translates domain names to IP addresses
- VN: Hệ thống chuyển đổi tên miền thành địa chỉ IP

### 5.2 Network Architecture
*Kiến trúc mạng*

**5.2.1 CIDR (Classless Inter-Domain Routing)**
- EN: Method for allocating IP addresses and routing
- VN: Phương pháp phân bổ địa chỉ IP và định tuyến

**5.2.2 BGP (Border Gateway Protocol)**
- EN: Protocol for routing between autonomous systems
- VN: Giao thức định tuyến giữa các hệ thống tự trị

**5.2.3 VPN (Virtual Private Network)**
- EN: Secure tunnel over public networks
- VN: Đường hầm bảo mật qua mạng công cộng

**5.2.4 CDN (Content Delivery Network)**
- EN: Geographically distributed servers for content delivery
- VN: Máy chủ phân tán địa lý để phân phối nội dung

### 5.3 Load Balancing
*Cân bằng tải*

**5.3.1 Application Load Balancer (ALB)**
- EN: Layer 7 load balancer for HTTP/HTTPS traffic
- VN: Cân bằng tải lớp 7 cho lưu lượng HTTP/HTTPS

**5.3.2 Network Load Balancer (NLB)**
- EN: Layer 4 load balancer for TCP/UDP traffic
- VN: Cân bằng tải lớp 4 cho lưu lượng TCP/UDP

**5.3.3 Gateway Load Balancer (GLB)**
- EN: Layer 3 load balancer for third-party appliances
- VN: Cân bằng tải lớp 3 cho thiết bị bên thứ ba

---

## 6. AWS Architecture Patterns
*Mẫu kiến trúc AWS*

### 6.1 High Availability
*Tính khả dụng cao*

**6.1.1 Auto Scaling**
- EN: Automatically adjusts capacity based on demand
- VN: Tự động điều chỉnh dung lượng dựa trên nhu cầu

**6.1.2 Multi-AZ (Availability Zone)**
- EN: Deploying resources across multiple data centers
- VN: Triển khai tài nguyên qua nhiều trung tâm dữ liệu

**6.1.3 Fault Tolerance**
- EN: System's ability to continue operating despite failures
- VN: Khả năng hệ thống tiếp tục hoạt động dù có lỗi

### 6.2 Performance & Scalability
*Hiệu suất & Khả năng mở rộng*

**6.2.1 Elastic**
- EN: Ability to scale resources up/down automatically
- VN: Khả năng tự động mở rộng/thu hẹp tài nguyên

**6.2.2 Caching**
- EN: Storing frequently accessed data for faster retrieval
- VN: Lưu trữ dữ liệu thường truy cập để truy xuất nhanh hơn

**6.2.3 Edge Location**
- EN: AWS data centers for content caching worldwide
- VN: Trung tâm dữ liệu AWS để cache nội dung toàn cầu

---

## 7. AWS Pricing & Cost Optimization
*Định giá & Tối ưu chi phí AWS*

### 7.1 Pricing Models
*Mô hình định giá*

**7.1.1 On-Demand**
- EN: Pay-as-you-use pricing with no commitments
- VN: Định giá trả theo sử dụng không cam kết

**7.1.2 Reserved Instances**
- EN: Discounted pricing for committed usage terms
- VN: Định giá giảm giá cho cam kết sử dụng

**7.1.3 Spot Instances**
- EN: Bid-based pricing for unused EC2 capacity
- VN: Định giá đấu thầu cho dung lượng EC2 không sử dụng

### 7.2 Cost Management
*Quản lý chi phí*

**7.2.1 Cost Explorer**
- EN: Tool for visualizing and analyzing AWS costs
- VN: Công cụ trực quan hóa và phân tích chi phí AWS

**7.2.2 Budgets**
- EN: Service for setting cost and usage budgets
- VN: Dịch vụ thiết lập ngân sách chi phí và sử dụng

**7.2.3 Trusted Advisor**
- EN: Service providing optimization recommendations
- VN: Dịch vụ cung cấp khuyến nghị tối ưu hóa

---

*End of Keywords Reference / Kết thúc tài liệu tham khảo từ khóa*