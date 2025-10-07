# AWS & Networking Keywords Reference
*Tài liệu tham khảo từ khóa AWS & Mạng*

## AWS SAA-C03 Exam Categories
*Các danh mục chứng chỉ AWS SAA-C03*

**🏗️ Design Resilient Architectures** - Thiết kế kiến trúc đàn hồi
**⚡ Design High-Performing Architectures** - Thiết kế kiến trúc hiệu suất cao  
**🔒 Design Secure Applications** - Thiết kế ứng dụng bảo mật
**💰 Design Cost-Optimized Architectures** - Thiết kế kiến trúc tối ưu chi phí

---

## 1. AWS Core Services
*Các dịch vụ cốt lõi AWS*

### 1.1 Compute Services
*Dịch vụ tính toán*

**1.1.1 EC2 (Elastic Compute Cloud)** 🏗️⚡💰
- EN: Virtual servers in the cloud with scalable computing capacity
- VN: Máy chủ ảo trên cloud với khả năng mở rộng tính toán
- **Purpose/Mục đích:** Host applications, websites, databases
- **Use Case/Trường hợp:** Web servers, application backends, batch processing

**1.1.2 Lambda** 🏗️⚡💰
- EN: Serverless compute service that runs code without managing servers
- VN: Dịch vụ tính toán không máy chủ chạy code mà không cần quản lý server
- **Purpose/Mục đích:** Event-driven code execution without server management
- **Use Case/Trường hợp:** API backends, file processing, scheduled tasks

**1.1.3 ECS (Elastic Container Service)** 🏗️⚡
- EN: Container orchestration service for Docker containers
- VN: Dịch vụ điều phối container cho Docker containers
- **Purpose/Mục đích:** Manage and scale containerized applications
- **Use Case/Trường hợp:** Microservices, container orchestration, CI/CD pipelines

**1.1.4 EKS (Elastic Kubernetes Service)** 🏗️⚡
- EN: Managed Kubernetes service for container orchestration
- VN: Dịch vụ Kubernetes được quản lý cho điều phối container
- **Purpose/Mục đích:** Run Kubernetes without managing control plane
- **Use Case/Trường hợp:** Complex microservices, enterprise container workloads

### 1.2 Storage Services
*Dịch vụ lưu trữ*

**1.2.1 S3 (Simple Storage Service)** 🏗️⚡🔒💰
- EN: Object storage service with unlimited scalability
- VN: Dịch vụ lưu trữ đối tượng với khả năng mở rộng không giới hạn
- **Purpose/Mục đích:** Store and retrieve any amount of data from anywhere
- **Use Case/Trường hợp:** Static websites, backups, data lakes, content distribution

**1.2.2 EBS (Elastic Block Store)** 🏗️⚡💰
- EN: Block-level storage volumes for EC2 instances
- VN: Ổ đĩa lưu trữ khối cho các EC2 instances
- **Purpose/Mục đích:** Persistent block storage for EC2 instances
- **Use Case/Trường hợp:** Database storage, file systems, boot volumes

**1.2.3 EFS (Elastic File System)** 🏗️⚡💰
- EN: Fully managed NFS file system for EC2
- VN: Hệ thống file NFS được quản lý hoàn toàn cho EC2
- **Purpose/Mục đích:** Shared file storage across multiple EC2 instances
- **Use Case/Trường hợp:** Content repositories, web serving, data analytics

**1.2.4 Glacier** 🏗️💰
- EN: Low-cost archive storage for long-term backup
- VN: Lưu trữ lưu trữ chi phí thấp cho sao lưu dài hạn
- **Purpose/Mục đích:** Long-term archival and backup at low cost
- **Use Case/Trường hợp:** Data archiving, compliance, disaster recovery

**1.2.5 Storage Gateway** 🏗️💰
- EN: Hybrid cloud storage service connecting on-premises to AWS
- VN: Dịch vụ lưu trữ hybrid cloud kết nối on-premises với AWS
- **Purpose/Mục đích:** Seamlessly connect on-premises to cloud storage
- **Use Case/Trường hợp:** Hybrid cloud storage, backup to cloud, migration

### 1.3 Database Services
*Dịch vụ cơ sở dữ liệu*

**1.3.1 RDS (Relational Database Service)** 🏗️⚡💰
- EN: Managed relational database service (MySQL, PostgreSQL, etc.)
- VN: Dịch vụ cơ sở dữ liệu quan hệ được quản lý
- **Purpose/Mục đích:** Managed relational databases without infrastructure management
- **Use Case/Trường hợp:** Web applications, enterprise apps, OLTP workloads

**1.3.2 DynamoDB** 🏗️⚡💰
- EN: NoSQL database service with single-digit millisecond performance
- VN: Dịch vụ cơ sở dữ liệu NoSQL với hiệu suất millisecond
- **Purpose/Mục đích:** Fast, scalable NoSQL database for any scale
- **Use Case/Trường hợp:** Mobile apps, gaming, IoT, real-time analytics

**1.3.3 Aurora** 🏗️⚡💰
- EN: MySQL and PostgreSQL compatible relational database
- VN: Cơ sở dữ liệu quan hệ tương thích MySQL và PostgreSQL
- **Purpose/Mục đích:** High-performance cloud-native relational database
- **Use Case/Trường hợp:** Enterprise applications, SaaS applications, web services

**1.3.4 ElastiCache** ⚡💰
- EN: In-memory caching service (Redis/Memcached)
- VN: Dịch vụ cache trong bộ nhớ
- **Purpose/Mục đích:** Improve application performance with sub-millisecond latency
- **Use Case/Trường hợp:** Session storage, database caching, real-time analytics

**1.3.5 Redshift** ⚡💰
- EN: Data warehouse service for analytics
- VN: Dịch vụ kho dữ liệu cho phân tích
- **Purpose/Mục đích:** Fast, scalable data warehouse for analytics
- **Use Case/Trường hợp:** Business intelligence, data analytics, reporting

---

## 2. AWS Networking Services
*Dịch vụ mạng AWS*

### 2.1 Core Networking
*Mạng cốt lõi*

**2.1.1 VPC (Virtual Private Cloud)** 🏗️🔒
- EN: Isolated virtual network within AWS cloud
- VN: Mạng ảo biệt lập trong AWS cloud
- **Purpose/Mục đích:** Create isolated network environment in AWS
- **Use Case/Trường hợp:** Secure application hosting, network isolation, hybrid connectivity

**2.1.2 Route 53** 🏗️⚡
- EN: Scalable DNS web service and domain registration
- VN: Dịch vụ DNS có thể mở rộng và đăng ký tên miền
- **Purpose/Mục đích:** Route end users to internet applications reliably
- **Use Case/Trường hợp:** Domain registration, DNS routing, health checks, failover

**2.1.3 CloudFront** 🏗️⚡🔒💰
- EN: Content Delivery Network (CDN) for fast content delivery
- VN: Mạng phân phối nội dung để phân phối nội dung nhanh
- **Purpose/Mục đích:** Deliver content with low latency and high transfer speeds
- **Use Case/Trường hợp:** Website acceleration, video streaming, API acceleration

**2.1.4 ELB (Elastic Load Balancer)** 🏗️⚡
- EN: Distributes incoming traffic across multiple targets
- VN: Phân phối lưu lượng truy cập đến nhiều mục tiêu
- **Purpose/Mục đích:** Distribute incoming application traffic across multiple targets
- **Use Case/Trường hợp:** High availability, fault tolerance, traffic distribution

**2.1.5 API Gateway** 🏗️⚡🔒💰
- EN: Service for creating, publishing, and managing APIs
- VN: Dịch vụ tạo, xuất bản và quản lý APIs
- **Purpose/Mục đích:** Create, publish, maintain, monitor, and secure APIs
- **Use Case/Trường hợp:** RESTful APIs, WebSocket APIs, serverless backends

### 2.2 VPC Components
*Thành phần VPC*

**2.2.1 Subnet** 🏗️🔒
- EN: Range of IP addresses in VPC, can be public or private
- VN: Dải địa chỉ IP trong VPC, có thể là công khai hoặc riêng tư
- **Purpose/Mục đích:** Segment VPC into smaller network ranges
- **Use Case/Trường hợp:** Network isolation, availability zones, security layers

**2.2.2 Internet Gateway (IGW)** 🏗️
- EN: Allows communication between VPC and internet
- VN: Cho phép giao tiếp giữa VPC và internet
- **Purpose/Mục đích:** Enable internet access for VPC resources
- **Use Case/Trường hợp:** Public subnet connectivity, web applications, public APIs

**2.2.3 NAT Gateway** 🏗️🔒💰
- EN: Enables private subnet instances to access internet
- VN: Cho phép các instance trong subnet riêng truy cập internet
- **Purpose/Mục đích:** Provide outbound internet access for private resources
- **Use Case/Trường hợp:** Software updates, API calls from private instances

**2.2.4 Route Table** 🏗️🔒
- EN: Contains rules (routes) that determine network traffic direction
- VN: Chứa các quy tắc xác định hướng lưu lượng mạng
- **Purpose/Mục đích:** Control traffic routing within VPC and to external networks
- **Use Case/Trường hợp:** Traffic routing, subnet associations, custom routing

**2.2.5 Security Group** 🔒
- EN: Virtual firewall controlling inbound/outbound traffic
- VN: Tường lửa ảo kiểm soát lưu lượng vào/ra
- **Purpose/Mục đích:** Control traffic at instance level with stateful rules
- **Use Case/Trường hợp:** Instance-level security, application access control

**2.2.6 NACL (Network Access Control List)** 🔒
- EN: Subnet-level firewall with allow/deny rules
- VN: Tường lửa cấp subnet với quy tắc cho phép/từ chối
- **Purpose/Mục đích:** Control traffic at subnet level with stateless rules
- **Use Case/Trường hợp:** Subnet-level security, defense in depth, compliance

### 2.3 Connectivity Services
*Dịch vụ kết nối*

**2.3.1 VPN Gateway** 🏗️🔒💰
- EN: Connects on-premises networks to VPC via VPN
- VN: Kết nối mạng on-premises với VPC qua VPN
- **Purpose/Mục đích:** Secure connection between on-premises and AWS
- **Use Case/Trường hợp:** Hybrid cloud, secure remote access, site-to-site connectivity

**2.3.2 Direct Connect** 🏗️⚡💰
- EN: Dedicated network connection from premises to AWS
- VN: Kết nối mạng chuyên dụng từ cơ sở hạ tầng đến AWS
- **Purpose/Mục đích:** High-bandwidth, low-latency connection to AWS
- **Use Case/Trường hợp:** Large data transfers, consistent network performance

**2.3.3 Transit Gateway** 🏗️💰
- EN: Network hub connecting VPCs and on-premises networks
- VN: Hub mạng kết nối các VPC và mạng on-premises
- **Purpose/Mục đích:** Simplify network connectivity between multiple VPCs
- **Use Case/Trường hợp:** Multi-VPC architectures, complex network topologies

**2.3.4 VPC Peering** 🏗️🔒
- EN: Network connection between two VPCs
- VN: Kết nối mạng giữa hai VPC
- **Purpose/Mục đích:** Enable direct communication between VPCs
- **Use Case/Trường hợp:** Cross-VPC communication, shared services, multi-region

---

## 3. AWS Security & Identity
*Bảo mật & Danh tính AWS*

### 3.1 Identity Services
*Dịch vụ danh tính*

**3.1.1 IAM (Identity and Access Management)** 🔒
- EN: Service for managing users, groups, and permissions
- VN: Dịch vụ quản lý người dùng, nhóm và quyền
- **Purpose/Mục đích:** Control access to AWS services and resources
- **Use Case/Trường hợp:** User management, role-based access, service permissions

**3.1.2 Cognito** 🔒
- EN: User identity and authentication service for web/mobile apps
- VN: Dịch vụ danh tính và xác thực người dùng cho ứng dụng web/mobile
- **Purpose/Mục đích:** Add user sign-up, sign-in, and access control to apps
- **Use Case/Trường hợp:** Mobile apps, web applications, user pools, identity federation

**3.1.3 SSO (Single Sign-On)** 🔒💰
- EN: Centrally manage access to multiple AWS accounts
- VN: Quản lý truy cập tập trung đến nhiều tài khoản AWS
- **Purpose/Mục đích:** Simplify access management across multiple AWS accounts
- **Use Case/Trường hợp:** Enterprise authentication, multi-account management

### 3.2 Security Services
*Dịch vụ bảo mật*

**3.2.1 WAF (Web Application Firewall)** 🔒
- EN: Protects web applications from common exploits
- VN: Bảo vệ ứng dụng web khỏi các cuộc tấn công phổ biến
- **Purpose/Mục đích:** Filter malicious web traffic before it reaches applications
- **Use Case/Trường hợp:** SQL injection protection, XSS prevention, rate limiting

**3.2.2 Shield** 🔒💰
- EN: DDoS protection service for AWS applications
- VN: Dịch vụ bảo vệ DDoS cho ứng dụng AWS
- **Purpose/Mục đích:** Protect against DDoS attacks
- **Use Case/Trường hợp:** DDoS mitigation, always-on protection, advanced threat protection

**3.2.3 GuardDuty** 🔒
- EN: Threat detection service using machine learning
- VN: Dịch vụ phát hiện mối đe dọa sử dụng machine learning
- **Purpose/Mục đích:** Detect malicious activity and unauthorized behavior
- **Use Case/Trường hợp:** Security monitoring, threat intelligence, incident response

**3.2.4 KMS (Key Management Service)** 🔒
- EN: Managed service for creating and controlling encryption keys
- VN: Dịch vụ được quản lý để tạo và kiểm soát khóa mã hóa
- **Purpose/Mục đích:** Create and manage cryptographic keys for encryption
- **Use Case/Trường hợp:** Data encryption, key rotation, compliance requirements

---

## 4. AWS Management & Monitoring
*Quản lý & Giám sát AWS*

### 4.1 Monitoring Services
*Dịch vụ giám sát*

**4.1.1 CloudWatch** 🏗️⚡🔒💰
- EN: Monitoring service for AWS resources and applications
- VN: Dịch vụ giám sát cho tài nguyên và ứng dụng AWS
- **Purpose/Mục đích:** Monitor resources, collect metrics, set alarms
- **Use Case/Trường hợp:** Performance monitoring, alerting, log analysis, auto scaling

**4.1.2 CloudTrail** 🔒
- EN: Service for logging and monitoring API calls
- VN: Dịch vụ ghi log và giám sát các lời gọi API
- **Purpose/Mục đích:** Track user activity and API usage across AWS
- **Use Case/Trường hợp:** Compliance auditing, security analysis, troubleshooting

**4.1.3 Config** 🔒💰
- EN: Service for assessing and auditing AWS resource configurations
- VN: Dịch vụ đánh giá và kiểm toán cấu hình tài nguyên AWS
- **Purpose/Mục đích:** Track resource configurations and compliance
- **Use Case/Trường hợp:** Configuration compliance, change management, auditing

### 4.2 Deployment Services
*Dịch vụ triển khai*

**4.2.1 CloudFormation** 🏗️💰
- EN: Infrastructure as Code service using templates
- VN: Dịch vụ Infrastructure as Code sử dụng templates
- **Purpose/Mục đích:** Model and provision AWS resources using code
- **Use Case/Trường hợp:** Infrastructure automation, consistent deployments, version control

**4.2.2 CodeDeploy** 🏗️
- EN: Automated application deployment service
- VN: Dịch vụ triển khai ứng dụng tự động
- **Purpose/Mục đích:** Automate code deployments to compute services
- **Use Case/Trường hợp:** Blue/green deployments, rolling deployments, CI/CD pipelines

**4.2.3 Elastic Beanstalk** 🏗️💰
- EN: Platform service for deploying web applications
- VN: Dịch vụ nền tảng để triển khai ứng dụng web
- **Purpose/Mục đích:** Deploy and manage applications without infrastructure complexity
- **Use Case/Trường hợp:** Web applications, API backends, development environments

---

## 5. Networking Fundamentals
*Kiến thức mạng cơ bản*

### 5.1 Network Protocols
*Giao thức mạng*

**5.1.1 TCP (Transmission Control Protocol)** 🏗️⚡
- EN: Reliable, connection-oriented protocol for data transmission
- VN: Giao thức kết nối đáng tin cậy để truyền dữ liệu
- **Purpose/Mục đích:** Ensure reliable, ordered data delivery
- **Use Case/Trường hợp:** Web browsing, email, file transfer, database connections

**5.1.2 UDP (User Datagram Protocol)** ⚡
- EN: Fast, connectionless protocol for data transmission
- VN: Giao thức không kết nối nhanh để truyền dữ liệu
- **Purpose/Mục đích:** Fast data transmission without reliability guarantees
- **Use Case/Trường hợp:** Video streaming, gaming, DNS queries, real-time applications

**5.1.3 HTTP/HTTPS** 🔒
- EN: Web protocols for transferring web content (secure version)
- VN: Giao thức web để truyền nội dung web (phiên bản bảo mật)
- **Purpose/Mục đích:** Transfer web content securely over the internet
- **Use Case/Trường hợp:** Web applications, APIs, secure communications

**5.1.4 DNS (Domain Name System)** 🏗️⚡
- EN: System that translates domain names to IP addresses
- VN: Hệ thống chuyển đổi tên miền thành địa chỉ IP
- **Purpose/Mục đích:** Resolve human-readable names to IP addresses
- **Use Case/Trường hợp:** Domain resolution, load balancing, service discovery

### 5.2 Network Architecture
*Kiến trúc mạng*

**5.2.1 CIDR (Classless Inter-Domain Routing)** 🏗️🔒
- EN: Method for allocating IP addresses and routing
- VN: Phương pháp phân bổ địa chỉ IP và định tuyến
- **Purpose/Mục đích:** Efficiently allocate IP addresses and enable flexible subnetting
- **Use Case/Trường hợp:** VPC design, subnet planning, network segmentation

**5.2.2 BGP (Border Gateway Protocol)** 🏗️⚡
- EN: Protocol for routing between autonomous systems
- VN: Giao thức định tuyến giữa các hệ thống tự trị
- **Purpose/Mục đích:** Route traffic between different networks on the internet
- **Use Case/Trường hợp:** Internet routing, multi-homed networks, traffic engineering

**5.2.3 VPN (Virtual Private Network)** 🔒💰
- EN: Secure tunnel over public networks
- VN: Đường hầm bảo mật qua mạng công cộng
- **Purpose/Mục đích:** Create secure connections over untrusted networks
- **Use Case/Trường hợp:** Remote access, site-to-site connectivity, secure communications

**5.2.4 CDN (Content Delivery Network)** ⚡💰
- EN: Geographically distributed servers for content delivery
- VN: Máy chủ phân tán địa lý để phân phối nội dung
- **Purpose/Mục đích:** Deliver content faster by caching near users
- **Use Case/Trường hợp:** Website acceleration, video streaming, global content distribution

### 5.3 Load Balancing
*Cân bằng tải*

**5.3.1 Application Load Balancer (ALB)** 🏗️⚡💰
- EN: Layer 7 load balancer for HTTP/HTTPS traffic
- VN: Cân bằng tải lớp 7 cho lưu lượng HTTP/HTTPS
- **Purpose/Mục đích:** Distribute HTTP/HTTPS requests with advanced routing
- **Use Case/Trường hợp:** Web applications, microservices, content-based routing

**5.3.2 Network Load Balancer (NLB)** 🏗️⚡
- EN: Layer 4 load balancer for TCP/UDP traffic
- VN: Cân bằng tải lớp 4 cho lưu lượng TCP/UDP
- **Purpose/Mục đích:** High-performance load balancing for TCP/UDP traffic
- **Use Case/Trường hợp:** Gaming applications, IoT, ultra-low latency requirements

**5.3.3 Gateway Load Balancer (GLB)** 🏗️🔒
- EN: Layer 3 load balancer for third-party appliances
- VN: Cân bằng tải lớp 3 cho thiết bị bên thứ ba
- **Purpose/Mục đích:** Deploy and scale third-party network virtual appliances
- **Use Case/Trường hợp:** Firewalls, intrusion detection, deep packet inspection

---

## 6. AWS Architecture Patterns
*Mẫu kiến trúc AWS*

### 6.1 High Availability
*Tính khả dụng cao*

**6.1.1 Auto Scaling** 🏗️⚡💰
- EN: Automatically adjusts capacity based on demand
- VN: Tự động điều chỉnh dung lượng dựa trên nhu cầu
- **Purpose/Mục đích:** Maintain application availability and manage costs
- **Use Case/Trường hợp:** Traffic spikes, cost optimization, maintaining performance

**6.1.2 Multi-AZ (Availability Zone)** 🏗️
- EN: Deploying resources across multiple data centers
- VN: Triển khai tài nguyên qua nhiều trung tâm dữ liệu
- **Purpose/Mục đích:** Achieve high availability and fault tolerance
- **Use Case/Trường hợp:** Database failover, disaster recovery, eliminating single points of failure

**6.1.3 Fault Tolerance** 🏗️
- EN: System's ability to continue operating despite failures
- VN: Khả năng hệ thống tiếp tục hoạt động dù có lỗi
- **Purpose/Mục đích:** Maintain service availability during component failures
- **Use Case/Trường hợp:** Mission-critical applications, always-on services, redundant systems

### 6.2 Performance & Scalability
*Hiệu suất & Khả năng mở rộng*

**6.2.1 Elastic** ⚡💰
- EN: Ability to scale resources up/down automatically
- VN: Khả năng tự động mở rộng/thu hẹp tài nguyên
- **Purpose/Mục đích:** Adapt to changing demand while optimizing costs
- **Use Case/Trường hợp:** Variable workloads, cost optimization, handling traffic spikes

**6.2.2 Caching** ⚡💰
- EN: Storing frequently accessed data for faster retrieval
- VN: Lưu trữ dữ liệu thường truy cập để truy xuất nhanh hơn
- **Purpose/Mục đích:** Improve application performance and reduce backend load
- **Use Case/Trường hợp:** Database query optimization, API response caching, session storage

**6.2.3 Edge Location** ⚡💰
- EN: AWS data centers for content caching worldwide
- VN: Trung tâm dữ liệu AWS để cache nội dung toàn cầu
- **Purpose/Mục đích:** Deliver content closer to end users for better performance
- **Use Case/Trường hợp:** Global content delivery, reduced latency, improved user experience

---

## 7. AWS Pricing & Cost Optimization
*Định giá & Tối ưu chi phí AWS*

### 7.1 Pricing Models
*Mô hình định giá*

**7.1.1 On-Demand** 💰
- EN: Pay-as-you-use pricing with no commitments
- VN: Định giá trả theo sử dụng không cam kết
- **Purpose/Mục đích:** Flexible computing with no upfront costs or commitments
- **Use Case/Trường hợp:** Development, testing, unpredictable workloads, short-term needs

**7.1.2 Reserved Instances** 💰
- EN: Discounted pricing for committed usage terms
- VN: Định giá giảm giá cho cam kết sử dụng
- **Purpose/Mục đích:** Significant cost savings for steady-state workloads
- **Use Case/Trường hợp:** Production environments, predictable usage, long-term applications

**7.1.3 Spot Instances** 💰
- EN: Bid-based pricing for unused EC2 capacity
- VN: Định giá đấu thầu cho dung lượng EC2 không sử dụng
- **Purpose/Mục đích:** Access spare compute capacity at reduced costs
- **Use Case/Trường hợp:** Batch processing, fault-tolerant workloads, flexible applications

### 7.2 Cost Management
*Quản lý chi phí*

**7.2.1 Cost Explorer** 💰
- EN: Tool for visualizing and analyzing AWS costs
- VN: Công cụ trực quan hóa và phân tích chi phí AWS
- **Purpose/Mục đích:** Understand spending patterns and identify cost optimization opportunities
- **Use Case/Trường hợp:** Cost analysis, budget planning, spending trends, resource optimization

**7.2.2 Budgets** 💰
- EN: Service for setting cost and usage budgets
- VN: Dịch vụ thiết lập ngân sách chi phí và sử dụng
- **Purpose/Mục đích:** Monitor costs and usage against defined budgets
- **Use Case/Trường hợp:** Cost control, spending alerts, budget management, cost governance

**7.2.3 Trusted Advisor** 🏗️⚡🔒💰
- EN: Service providing optimization recommendations
- VN: Dịch vụ cung cấp khuyến nghị tối ưu hóa
- **Purpose/Mục đích:** Provide best practice recommendations across multiple categories
- **Use Case/Trường hợp:** Cost optimization, security improvements, performance tuning, fault tolerance

---

*End of Keywords Reference / Kết thúc tài liệu tham khảo từ khóa*