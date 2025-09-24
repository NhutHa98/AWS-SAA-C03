# 🎭 AWS SAA-C03 Practice Scenarios

> **Mục đích**: Thực hành với các tình huống thực tế thường gặp trong exam

---

## 🏢 **Scenario 1: E-commerce Platform Migration**

### **Business Context**
Công ty e-commerce hiện tại đang chạy trên on-premises với:
- Web application (PHP/MySQL)
- 50,000 users/day, peak traffic vào cuối tuần
- Database 200GB, backup hàng đêm
- Requirement: 99.9% uptime, < 2 giây response time

### **Requirements**
- ✅ **High Availability**: Multi-AZ deployment
- ✅ **Scalability**: Handle traffic spikes
- ✅ **Security**: PCI DSS compliance for payment processing
- ✅ **Cost-effective**: Optimize for variable workload
- ✅ **Global**: Users từ US, Europe, Asia

### **Architecture Solution**

```
Internet → CloudFront → WAF → ALB → Auto Scaling Group (EC2)
                                  ↓
                              Private Subnets → RDS Multi-AZ + Read Replicas
                                  ↓
                              ElastiCache (Redis) → S3 (static assets)
```

**Detailed Components**:

1. **Global Distribution**:
   - **CloudFront** với multiple origins (ALB, S3)
   - **Route 53** với latency-based routing
   - **Edge locations** tại US, Europe, Asia

2. **Web Tier**:
   - **ALB** across 3 AZs
   - **Auto Scaling Group** với target tracking (CPU 70%)
   - **EC2 instances** t3.medium (burstable performance)
   - **Security Groups** chỉ allow HTTP/HTTPS từ ALB

3. **Application Tier**:
   - **Private subnets** trong 3 AZs
   - **Application Load Balancer** internal cho microservices
   - **ECS Fargate** cho containerized services
   - **Lambda** cho event processing (orders, notifications)

4. **Database Tier**:
   - **RDS MySQL** Multi-AZ trong private subnets
   - **Read Replicas** cho read scaling
   - **ElastiCache Redis** cluster mode cho session store
   - **DynamoDB** cho shopping cart (session data)

5. **Storage**:
   - **S3** cho product images, static assets
   - **S3 Intelligent Tiering** cho cost optimization
   - **EBS gp3** cho EC2 instances
   - **EFS** cho shared application files

6. **Security**:
   - **WAF** với rules cho OWASP Top 10
   - **SSL termination** tại ALB
   - **KMS encryption** cho RDS và S3
   - **VPC Flow Logs** cho network monitoring
   - **GuardDuty** cho threat detection

7. **Monitoring & Logging**:
   - **CloudWatch** metrics và alarms
   - **CloudTrail** cho API auditing
   - **Application Insights** cho performance monitoring
   - **X-Ray** cho distributed tracing

### **Cost Optimization Strategy**
- **Reserved Instances** cho baseline capacity (40% workload)
- **Spot Instances** cho batch processing (image resize, reports)
- **Auto Scaling** cho variable traffic
- **S3 Lifecycle policies** cho log retention
- **CloudWatch cost monitoring** với budgets

### **Exam Questions Style**

**Q1: Làm thế nào để handle traffic spike trong Black Friday (10x normal)?**
<details>
<summary>Đáp án</summary>

- **Predictive Scaling**: Cấu hình trước peak time
- **CloudFront**: Cache static content globally  
- **ElastiCache**: Cache database queries
- **RDS Read Replicas**: Thêm read replicas tạm thời
- **DynamoDB On-Demand**: Auto scale for cart data
- **Lambda Concurrency**: Provisioned concurrency cho critical functions

</details>

**Q2: Ensure PCI DSS compliance cho payment processing?**
<details>
<summary>Đáp án</summary>

- **Network Segmentation**: Separate VPC cho payment processing
- **Encryption**: KMS cho data at rest, SSL/TLS in transit
- **Access Control**: IAM roles, MFA, least privilege
- **Monitoring**: CloudTrail, Config rules, GuardDuty
- **Data Isolation**: Dedicated tenancy cho sensitive workloads
- **Regular Audits**: AWS Config conformance packs

</details>

---

## 🏥 **Scenario 2: Healthcare Data Analytics Platform**

### **Business Context**
Hospital cần xây dựng platform phân tích dữ liệu y tế:
- 10TB medical images/month
- Real-time patient monitoring data
- HIPAA compliance requirements
- Machine learning for diagnosis support
- Research data sharing với universities

### **Requirements**
- ✅ **HIPAA Compliance**: Encryption, audit trails, access controls
- ✅ **Real-time Processing**: IoT sensors, patient monitors
- ✅ **Data Lake**: Structured và unstructured data
- ✅ **Machine Learning**: Medical image analysis
- ✅ **Disaster Recovery**: RTO 4 hours, RPO 15 minutes

### **Architecture Solution**

```
IoT Devices → Kinesis Data Streams → Lambda → DynamoDB
     ↓                                    ↓
Medical Images → S3 → Lambda → SageMaker → QuickSight
     ↓
Glue ETL → Redshift ← Analytics Users
```

**Detailed Components**:

1. **Data Ingestion**:
   - **Kinesis Data Streams** cho real-time IoT data
   - **S3 Transfer Acceleration** cho medical images upload
   - **Direct Connect** cho on-premises systems
   - **DataSync** cho large file transfers

2. **Data Lake**:
   - **S3** với separate buckets cho different data types
   - **Lake Formation** cho data governance
   - **Glue Catalog** cho metadata management
   - **Partitioning** by date/department for performance

3. **Real-time Processing**:
   - **Lambda** functions cho stream processing
   - **DynamoDB** cho patient monitoring alerts
   - **SNS** cho notification system
   - **EventBridge** cho workflow orchestration

4. **Batch Processing**:
   - **Glue ETL** jobs cho data transformation
   - **EMR** cho large-scale data processing
   - **Step Functions** cho complex workflows
   - **Batch** cho medical image processing

5. **Analytics & ML**:
   - **Redshift** cho structured analytics
   - **Athena** cho ad-hoc querying
   - **SageMaker** cho ML model training/deployment
   - **QuickSight** cho dashboards và reports

6. **Security & Compliance**:
   - **KMS** với customer-managed keys
   - **VPC Endpoints** cho private access
   - **CloudTrail** với log file integrity validation
   - **Config** rules cho HIPAA compliance
   - **Macie** cho PII discovery trong S3

### **HIPAA Compliance Checklist**
- [ ] **Encryption**: At rest (KMS) và in transit (TLS)
- [ ] **Access Controls**: IAM roles, resource-based policies
- [ ] **Audit Logging**: CloudTrail, VPC Flow Logs
- [ ] **Data Backup**: Automated backups, cross-region replication
- [ ] **Network Security**: Private subnets, security groups
- [ ] **Business Associate Agreement**: Signed với AWS

### **Exam Questions Style**

**Q: How to ensure HIPAA compliance for medical data in S3?**
<details>
<summary>Đáp án</summary>

- **Server-Side Encryption**: SSE-KMS với customer-managed keys
- **Bucket Policies**: Restrict access, require encrypted uploads
- **VPC Endpoints**: Private access without internet
- **CloudTrail**: Log all S3 API calls
- **Macie**: Identify and protect PHI
- **Versioning & MFA Delete**: Protect against accidental deletion
- **Cross-Region Replication**: Encrypted replication for DR

</details>

---

## 🏭 **Scenario 3: Manufacturing IoT Platform**

### **Business Context**
Manufacturing company với 50 factories worldwide:
- 10,000 IoT sensors per factory
- Real-time equipment monitoring
- Predictive maintenance alerts
- Supply chain optimization
- Edge processing requirements

### **Requirements**
- ✅ **Edge Computing**: Process data locally
- ✅ **Real-time Analytics**: Equipment anomaly detection  
- ✅ **Global Scale**: Multi-region deployment
- ✅ **Cost Optimization**: Handle massive data volumes
- ✅ **Integration**: SAP, Oracle systems

### **Architecture Solution**

```
Factory Floor → IoT Greengrass → Kinesis → Lambda → DynamoDB
      ↓              ↓              ↓        ↓
   Edge ML → Local Processing → Firehose → S3 → Athena
                                          ↓
                                     Glue ETL → Redshift
```

**Detailed Components**:

1. **Edge Computing**:
   - **IoT Greengrass** cho local processing
   - **Lambda@Edge** cho real-time decisions
   - **Local storage** với SSD caching
   - **Intermittent connectivity** handling

2. **Data Streaming**:
   - **Kinesis Data Streams** cho real-time ingestion
   - **Kinesis Data Firehose** cho S3 delivery
   - **Kinesis Analytics** cho streaming SQL
   - **Producer sharding** for high throughput

3. **Storage Strategy**:
   - **S3** với intelligent tiering
   - **Partition strategy**: factory/date/hour
   - **Compression**: Parquet format
   - **Lifecycle policies** for cost optimization

4. **Analytics Pipeline**:
   - **Glue** cho data cataloging và ETL
   - **Athena** cho ad-hoc analysis
   - **EMR** cho complex analytics
   - **SageMaker** cho predictive maintenance ML

### **Cost Optimization for IoT Data**
- **Data Compression**: Reduce storage costs by 60-80%
- **Partitioning**: Improve query performance, reduce costs
- **S3 Storage Classes**: Move old data to IA/Glacier
- **Spot Instances**: For EMR batch processing
- **Reserved Capacity**: For DynamoDB predictable workloads

---

## 🏦 **Scenario 4: Financial Services Disaster Recovery**

### **Business Context**
Investment firm cần DR solution:
- Trading applications (microsecond latency)
- Compliance data retention (7 years)
- Real-time risk calculations
- 24/7 operations, zero downtime tolerance
- Regulatory requirements (SOX, Basel III)

### **Requirements**
- ✅ **RTO**: 30 minutes for critical systems
- ✅ **RPO**: 5 minutes maximum data loss
- ✅ **Compliance**: Data residency, audit trails
- ✅ **Performance**: Ultra-low latency trading
- ✅ **Security**: Multi-factor authentication, encryption

### **DR Strategy: Pilot Light → Warm Standby**

**Primary Region (us-east-1)**:
- Production trading systems
- Real-time databases
- Full capacity infrastructure

**DR Region (us-west-2)**:
- **Pilot Light**: Core AMIs, minimal RDS instances
- **Automated scaling**: CloudFormation StackSets
- **Data Replication**: Cross-region replicas
- **DNS Failover**: Route 53 health checks

### **Implementation Details**:

1. **Database Replication**:
   - **Aurora Global Database**: <1 second lag
   - **DynamoDB Global Tables**: Multi-master replication
   - **ElastiCache**: Redis with backup/restore
   - **Cross-region snapshots**: Hourly automated

2. **Application Deployment**:
   - **AMI replication**: Cross-region AMI copy
   - **ECS task definitions**: Multi-region deployment
   - **Lambda functions**: Cross-region deployment
   - **Container registry**: ECR replication

3. **Network Preparation**:
   - **VPC Peering**: Pre-established connections
   - **Direct Connect**: Redundant connections
   - **VPN Backup**: Site-to-site VPN
   - **DNS**: Route 53 with health checks

### **Exam Questions Style**

**Q: How to achieve 30-minute RTO for trading applications?**
<details>
<summary>Đáp án</summary>

**Warm Standby approach**:
- **Pre-deployed infrastructure**: Smaller capacity in DR region
- **Database replicas**: Aurora Global Database với continuous replication
- **Automated scaling**: Lambda triggers to scale up DR environment
- **DNS failover**: Route 53 health check failover
- **Load balancer**: Pre-configured ALB in DR region
- **Testing**: Monthly DR drills với automated validation

</details>

---

## 📚 **Practice Question Patterns**

### **Pattern 1: Service Selection**
"A company needs to [specific requirement]. Which AWS service would you recommend?"

**Approach**:
1. Identify key requirements (performance, cost, scalability)
2. Match requirements to service capabilities
3. Consider integration with other services
4. Eliminate services that don't fit

### **Pattern 2: Architecture Design**
"Design a solution that provides [requirements list]"

**Approach**:
1. Break down into tiers (web, app, database)
2. Apply Well-Architected principles
3. Consider cross-cutting concerns (security, monitoring)
4. Validate against all requirements

### **Pattern 3: Problem Solving**
"A company is experiencing [problem]. How can this be resolved?"

**Approach**:
1. Identify root cause
2. Consider multiple solutions
3. Choose most appropriate based on constraints
4. Consider preventive measures

### **Pattern 4: Cost Optimization**
"How can a company reduce costs for [scenario]?"

**Approach**:
1. Analyze usage patterns
2. Identify optimization opportunities
3. Consider reserved capacity vs on-demand
4. Factor in operational overhead

---

**🎯 Practice with these scenarios regularly to build pattern recognition skills essential for the SAA-C03 exam!**