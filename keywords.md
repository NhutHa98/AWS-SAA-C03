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

### 1.4 Analytics Services
*Dịch vụ phân tích dữ liệu*

**1.4.1 Athena** ⚡💰
- EN: Serverless interactive query service for S3 data
- VN: Dịch vụ truy vấn tương tác không máy chủ cho dữ liệu S3
- **Purpose/Mục đích:** Run SQL queries directly on S3 data without infrastructure
- **Use Case/Trường hợp:** Ad-hoc analysis, log analysis, data lake queries

**1.4.2 AWS Glue** ⚡💰
- EN: Serverless ETL service for data preparation
- VN: Dịch vụ ETL không máy chủ để chuẩn bị dữ liệu
- **Purpose/Mục đích:** Extract, transform, and load data between data stores
- **Use Case/Trường hợp:** Data cataloging, ETL jobs, schema discovery

**1.4.3 EMR (Elastic MapReduce)** ⚡💰
- EN: Big data processing platform using Hadoop/Spark
- VN: Nền tảng xử lý big data sử dụng Hadoop/Spark
- **Purpose/Mục đích:** Process large datasets using distributed computing
- **Use Case/Trường hợp:** Big data analytics, machine learning, data science

**1.4.4 Kinesis Data Analytics** ⚡
- EN: Real-time stream processing with SQL
- VN: Xử lý luồng dữ liệu thời gian thực với SQL
- **Purpose/Mục đích:** Analyze streaming data in real-time
- **Use Case/Trường hợp:** Real-time dashboards, anomaly detection, live metrics

**1.4.5 QuickSight** 🏗️💰
- EN: Business intelligence and data visualization service
- VN: Dịch vụ business intelligence và trực quan hóa dữ liệu
- **Purpose/Mục đích:** Create interactive dashboards and reports
- **Use Case/Trường hợp:** Executive dashboards, self-service BI, embedded analytics

### 1.5 Data Transfer Services
*Dịch vụ truyền tải dữ liệu*

**1.5.1 Snowball Edge** 🏗️💰
- EN: Edge computing device with 80TB storage and compute capacity
- VN: Thiết bị edge computing với dung lượng 80TB và khả năng tính toán
- **Purpose/Mục đích:** Data transfer and edge computing in remote locations
- **Use Case/Trường hợp:** Large data migrations, edge processing, offline environments

**1.5.2 Snowcone** 🏗️💰
- EN: Small, portable edge computing device (8TB storage)
- VN: Thiết bị edge computing nhỏ gọn, di động (8TB)
- **Purpose/Mục đích:** Edge computing in space-constrained environments
- **Use Case/Trường hợp:** Drones, vehicles, remote locations, IoT edge processing

**1.5.3 Snowmobile** 🏗️💰
- EN: Exabyte-scale data transfer truck (100PB capacity)
- VN: Xe tải truyền dữ liệu quy mô exabyte (100PB)
- **Purpose/Mục đích:** Massive data center migrations
- **Use Case/Trường hợp:** Entire data center moves, legacy system consolidation

**1.5.4 DataSync** 🏗️💰
- EN: Online data transfer service for moving data between locations
- VN: Dịch vụ truyền dữ liệu online để di chuyển dữ liệu giữa các vị trí
- **Purpose/Mục đích:** Automated, secure data transfer over network
- **Use Case/Trường hợp:** Hybrid cloud sync, data lake ingestion, backup to cloud

**1.5.5 Transfer Family** 🏗️💰
- EN: Managed FTP, FTPS, and SFTP service
- VN: Dịch vụ FTP, FTPS và SFTP được quản lý
- **Purpose/Mục đích:** Secure file transfer protocols as managed service
- **Use Case/Trường hợp:** B2B file exchange, application integration, legacy system support

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

### 2.3 Messaging & Eventing Services
*Dịch vụ nhắn tin và sự kiện*

**2.3.1 SQS (Simple Queue Service)** 🏗️⚡💰
- EN: Fully managed message queuing service
- VN: Dịch vụ hàng đợi tin nhắn được quản lý hoàn toàn
- **Purpose/Mục đích:** Decouple application components with reliable messaging
- **Use Case/Trường hợp:** Job queues, order processing, microservices communication

**2.3.2 SNS (Simple Notification Service)** 🏗️⚡🔒
- EN: Fully managed pub/sub messaging service
- VN: Dịch vụ nhắn tin pub/sub được quản lý hoàn toàn
- **Purpose/Mục đích:** Send notifications to multiple subscribers simultaneously
- **Use Case/Trường hợp:** Push notifications, email alerts, fan-out messaging

**2.3.3 EventBridge** 🏗️⚡🔒
- EN: Serverless event bus for application integration
- VN: Event bus không máy chủ để tích hợp ứng dụng
- **Purpose/Mục đích:** Route events between AWS services and SaaS applications
- **Use Case/Trường hợp:** Event-driven architectures, SaaS integration, microservices

**2.3.4 Kinesis Data Streams** 🏗️⚡
- EN: Real-time data streaming service
- VN: Dịch vụ streaming dữ liệu thời gian thực
- **Purpose/Mục đích:** Collect and process streaming data in real-time
- **Use Case/Trường hợp:** Real-time analytics, log processing, IoT data ingestion

**2.3.5 Step Functions** 🏗️⚡
- EN: Visual workflow service for coordinating distributed applications
- VN: Dịch vụ quy trình làm việc trực quan để điều phối ứng dụng phân tán
- **Purpose/Mục đích:** Orchestrate multiple AWS services into workflows
- **Use Case/Trường hợp:** Business processes, data pipelines, error handling workflows

### 2.4 Connectivity Services
*Dịch vụ kết nối*

**2.4.1 VPN Gateway** 🏗️🔒💰
- EN: Connects on-premises networks to VPC via VPN
- VN: Kết nối mạng on-premises với VPC qua VPN
- **Purpose/Mục đích:** Secure connection between on-premises and AWS
- **Use Case/Trường hợp:** Hybrid cloud, secure remote access, site-to-site connectivity

**2.4.2 Direct Connect** 🏗️⚡💰
- EN: Dedicated network connection from premises to AWS
- VN: Kết nối mạng chuyên dụng từ cơ sở hạ tầng đến AWS
- **Purpose/Mục đích:** High-bandwidth, low-latency connection to AWS
- **Use Case/Trường hợp:** Large data transfers, consistent network performance

**2.4.3 Transit Gateway** 🏗️💰
- EN: Network hub connecting VPCs and on-premises networks
- VN: Hub mạng kết nối các VPC và mạng on-premises
- **Purpose/Mục đích:** Simplify network connectivity between multiple VPCs
- **Use Case/Trường hợp:** Multi-VPC architectures, complex network topologies

**2.4.4 VPC Peering** 🏗️🔒
- EN: Network connection between two VPCs
- VN: Kết nối mạng giữa hai VPC
- **Purpose/Mục đích:** Enable direct communication between VPCs
- **Use Case/Trường hợp:** Cross-VPC communication, shared services, multi-region

**2.4.5 Global Accelerator** 🏗️⚡💰
- EN: Network service that improves global application performance
- VN: Dịch vụ mạng cải thiện hiệu suất ứng dụng toàn cầu
- **Purpose/Mục đích:** Optimize global network performance using AWS backbone
- **Use Case/Trường hợp:** Gaming applications, IoT, real-time APIs, global load balancing

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

**3.2.5 Network Firewall** 🔒
- EN: Managed network firewall service with IPS capabilities
- VN: Dịch vụ tường lửa mạng được quản lý với khả năng IPS
- **Purpose/Mục đích:** Protect VPCs with managed firewall and intrusion prevention
- **Use Case/Trường hợp:** Network security, deep packet inspection, compliance

**3.2.6 Firewall Manager** 🔒💰
- EN: Centralized security policy management across accounts
- VN: Quản lý chính sách bảo mật tập trung qua các tài khoản
- **Purpose/Mục đích:** Manage security policies across multiple AWS accounts
- **Use Case/Trường hợp:** Multi-account governance, compliance enforcement, policy automation

**3.2.7 Traffic Mirroring** 🔒
- EN: Copy network traffic for analysis and security monitoring
- VN: Sao chép lưu lượng mạng để phân tích và giám sát bảo mật
- **Purpose/Mục đích:** Mirror VPC traffic to security analysis tools
- **Use Case/Trường hợp:** Network forensics, IDS/IPS, compliance monitoring

**3.2.8 Macie** 🔒💰
- EN: ML-powered data security service for discovering sensitive data
- VN: Dịch vụ bảo mật dữ liệu được hỗ trợ ML để khám phá dữ liệu nhạy cảm
- **Purpose/Mục đích:** Discover, classify, and protect sensitive data in S3
- **Use Case/Trường hợp:** PII discovery, data classification, compliance monitoring

**3.2.9 Secrets Manager** 🔒💰
- EN: Centralized secrets management with automatic rotation
- VN: Quản lý bí mật tập trung với xoay vòng tự động
- **Purpose/Mục đích:** Store, retrieve, and rotate application secrets
- **Use Case/Trường hợp:** Database credentials, API keys, application secrets

**3.2.10 IAM Access Analyzer** 🔒
- EN: Analyze resource policies to identify security risks
- VN: Phân tích chính sách tài nguyên để xác định rủi ro bảo mật
- **Purpose/Mục đích:** Identify overly permissive resource access policies
- **Use Case/Trường hợp:** Security assessment, policy validation, compliance auditing

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

### 5.4 Advanced Networking Concepts
*Khái niệm mạng nâng cao*

**5.4.1 SPICE (QuickSight)** ⚡💰
- EN: Super-fast, Parallel, In-memory Calculation Engine
- VN: Công cụ tính toán siêu nhanh, song song, trong bộ nhớ
- **Purpose/Mục đích:** High-performance in-memory analytics engine for QuickSight
- **Use Case/Trường hợp:** Fast dashboard queries, interactive analytics, large dataset processing

**5.4.2 NFS (Network File System)** 🏗️🔒
- EN: Protocol for accessing files over network as if local
- VN: Giao thức truy cập file qua mạng như file cục bộ
- **Purpose/Mục đích:** Mount remote file systems as local drives
- **Use Case/Trường hợp:** Shared storage, Snowball Edge data transfer, EFS access

**5.4.3 SMB (Server Message Block)** 🏗️🔒
- EN: Network file sharing protocol used primarily in Windows environments
- VN: Giao thức chia sẻ file mạng chủ yếu dùng trong môi trường Windows
- **Purpose/Mục đích:** Share files, printers, and resources over network
- **Use Case/Trường hợp:** Windows file sharing, Storage Gateway, cross-platform access

**5.4.4 GENEVE Protocol** 🔒
- EN: Generic Network Virtualization Encapsulation protocol
- VN: Giao thức đóng gói ảo hóa mạng chung
- **Purpose/Mục đích:** Network overlay protocol for Gateway Load Balancer
- **Use Case/Trường hợp:** Traffic mirroring, security appliance integration, network virtualization

**5.4.5 Anycast IP** ⚡🔒
- EN: Network addressing where single IP is advertised from multiple locations
- VN: Địa chỉ mạng nơi một IP được quảng cáo từ nhiều vị trí
- **Purpose/Mục đích:** Route traffic to nearest/best performing location
- **Use Case/Trường hợp:** Global Accelerator, DNS, DDoS mitigation

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

---

## 8. Data Analytics & Business Intelligence
*Phân tích dữ liệu & Business Intelligence*

### 8.1 Data Processing Concepts
*Khái niệm xử lý dữ liệu*

**8.1.1 ETL (Extract, Transform, Load)** ⚡💰
- EN: Process of extracting data from sources, transforming it, and loading into target
- VN: Quy trình trích xuất dữ liệu từ nguồn, chuyển đổi và tải vào đích
- **Purpose/Mục đích:** Prepare and integrate data from multiple sources
- **Use Case/Trường hợp:** Data warehousing, data lake preparation, system integration

**8.1.2 ELT (Extract, Load, Transform)** ⚡💰
- EN: Process of extracting data, loading into target, then transforming
- VN: Quy trình trích xuất dữ liệu, tải vào đích, sau đó chuyển đổi
- **Purpose/Mục đích:** Leverage target system's processing power for transformations
- **Use Case/Trường hợp:** Cloud data warehouses, big data platforms, modern analytics

**8.1.3 Data Lake** 🏗️💰
- EN: Centralized repository storing structured and unstructured data at scale
- VN: Kho lưu trữ tập trung chứa dữ liệu có cấu trúc và phi cấu trúc ở quy mô lớn
- **Purpose/Mục đích:** Store raw data in native format for future analysis
- **Use Case/Trường hợp:** Big data analytics, ML training data, exploratory analysis

**8.1.4 Data Warehouse** ⚡💰
- EN: Optimized database system for analytical queries and reporting
- VN: Hệ thống cơ sở dữ liệu được tối ưu hóa cho truy vấn phân tích và báo cáo
- **Purpose/Mục đích:** Structured data storage optimized for business intelligence
- **Use Case/Trường hợp:** Business reporting, OLAP, executive dashboards

**8.1.5 OLAP (Online Analytical Processing)** ⚡
- EN: Technology for fast analysis of multidimensional data
- VN: Công nghệ phân tích nhanh dữ liệu đa chiều
- **Purpose/Mục đích:** Enable complex analytical queries on large datasets
- **Use Case/Trường hợp:** Business intelligence, data mining, financial analysis

### 8.2 Streaming & Real-time Processing
*Xử lý streaming và thời gian thực*

**8.2.1 Stream Processing** ⚡
- EN: Processing data in real-time as it flows through the system
- VN: Xử lý dữ liệu thời gian thực khi nó chảy qua hệ thống
- **Purpose/Mục đích:** Analyze data immediately as it arrives
- **Use Case/Trường hợp:** Real-time analytics, fraud detection, IoT monitoring

**8.2.2 Batch Processing** 💰
- EN: Processing data in discrete chunks or batches
- VN: Xử lý dữ liệu theo từng khối hoặc lô riêng biệt
- **Purpose/Mục đích:** Process large volumes of data efficiently
- **Use Case/Trường hợp:** Daily reports, data warehouse loading, historical analysis

**8.2.3 Sharding** ⚡
- EN: Distributing data across multiple machines for parallel processing
- VN: Phân phối dữ liệu qua nhiều máy để xử lý song song
- **Purpose/Mục đích:** Scale processing power by distributing workload
- **Use Case/Trường hợp:** Kinesis data streams, database scaling, distributed computing

**8.2.4 Partition Key** ⚡
- EN: Key used to determine which shard or partition data belongs to
- VN: Khóa dùng để xác định dữ liệu thuộc shard hoặc phân vùng nào
- **Purpose/Mục đích:** Ensure related data is processed together
- **Use Case/Trường hợp:** Kinesis streams, DynamoDB, distributed databases

### 8.3 Business Intelligence Concepts
*Khái niệm Business Intelligence*

**8.3.1 KPI (Key Performance Indicator)** 📊
- EN: Measurable value demonstrating how effectively objectives are achieved
- VN: Giá trị có thể đo lường chứng minh mức độ đạt được mục tiêu
- **Purpose/Mục đích:** Track business performance against strategic goals
- **Use Case/Trường hợp:** Executive dashboards, performance monitoring, business reviews

**8.3.2 Drill Down** 📊
- EN: Navigation from summary to detailed level in data analysis
- VN: Điều hướng từ mức tóm tắt đến mức chi tiết trong phân tích dữ liệu
- **Purpose/Mục đích:** Explore data at different levels of granularity
- **Use Case/Trường hợp:** Interactive dashboards, root cause analysis, data exploration

**8.3.3 Cross-filtering** 📊
- EN: Selecting data in one visualization affects others on the same dashboard
- VN: Chọn dữ liệu trong một biểu đồ ảnh hưởng đến các biểu đồ khác cùng dashboard
- **Purpose/Mục đích:** Enable interactive exploration across related visuals
- **Use Case/Trường hợp:** Interactive dashboards, data discovery, contextual analysis

**8.3.4 Row-Level Security (RLS)** 🔒
- EN: Security model that restricts data access based on user characteristics
- VN: Mô hình bảo mật hạn chế truy cập dữ liệu dựa trên đặc điểm người dùng
- **Purpose/Mục đích:** Ensure users only see data they're authorized to access
- **Use Case/Trường hợp:** Multi-tenant dashboards, departmental reporting, data privacy

**8.3.5 Embedded Analytics** 📊💰
- EN: Integration of BI capabilities directly into business applications
- VN: Tích hợp khả năng BI trực tiếp vào ứng dụng kinh doanh
- **Purpose/Mục đích:** Provide analytics within existing user workflows
- **Use Case/Trường hợp:** Customer portals, SaaS applications, internal tools

### 8.4 Data Formats & Storage
*Định dạng dữ liệu và lưu trữ*

**8.4.1 Parquet** ⚡💰
- EN: Columnar storage file format optimized for analytics
- VN: Định dạng file lưu trữ cột được tối ưu hóa cho phân tích
- **Purpose/Mục đích:** Efficient storage and querying of analytical data
- **Use Case/Trường hợp:** Data lakes, Athena queries, Spark processing

**8.4.2 ORC (Optimized Row Columnar)** ⚡💰
- EN: Columnar storage format with compression and indexing
- VN: Định dạng lưu trữ cột với nén và lập chỉ mục
- **Purpose/Mục đích:** High-performance storage for Hive-based analytics
- **Use Case/Trường hợp:** EMR processing, Hive queries, big data analytics

**8.4.3 Avro** ⚡
- EN: Schema evolution-friendly serialization format
- VN: Định dạng serialization thân thiện với sự phát triển schema
- **Purpose/Mục đích:** Flexible data serialization with schema evolution support
- **Use Case/Trường hợp:** Streaming data, schema evolution, Kafka messages

**8.4.4 Delta Lake** ⚡
- EN: Storage layer providing ACID transactions on top of data lakes
- VN: Lớp lưu trữ cung cấp giao dịch ACID trên data lake
- **Purpose/Mục đích:** Reliable data lakes with transactional consistency
- **Use Case/Trường hợp:** Data lake reliability, time travel, concurrent access

---

## 9. Machine Learning & AI Services
*Dịch vụ Machine Learning và AI*

### 9.1 ML Platform Services
*Dịch vụ nền tảng ML*

**9.1.1 SageMaker** 🏗️⚡💰
- EN: Fully managed machine learning platform
- VN: Nền tảng machine learning được quản lý hoàn toàn
- **Purpose/Mục đích:** Build, train, and deploy ML models at scale
- **Use Case/Trường hợp:** Model development, ML pipelines, model hosting

**9.1.2 Comprehend** ⚡💰
- EN: Natural language processing service for text analysis
- VN: Dịch vụ xử lý ngôn ngữ tự nhiên để phân tích văn bản
- **Purpose/Mục đích:** Extract insights from text using NLP
- **Use Case/Trường hợp:** Sentiment analysis, entity extraction, document classification

**9.1.3 Rekognition** ⚡💰
- EN: Image and video analysis service using deep learning
- VN: Dịch vụ phân tích hình ảnh và video sử dụng deep learning
- **Purpose/Mục đích:** Analyze images and videos for objects, faces, and activities
- **Use Case/Trường hợp:** Content moderation, facial recognition, object detection

**9.1.4 Textract** ⚡💰
- EN: Extract text and data from documents using OCR and ML
- VN: Trích xuất văn bản và dữ liệu từ tài liệu sử dụng OCR và ML
- **Purpose/Mục đích:** Automatically extract structured data from documents
- **Use Case/Trường hợp:** Document processing, form analysis, invoice processing

---

*End of Keywords Reference / Kết thúc tài liệu tham khảo từ khóa*