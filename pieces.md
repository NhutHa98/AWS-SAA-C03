| Type of Analysis         | Recommended AWS Service    | Description                                      |
| ------------------------ | -------------------------- | ------------------------------------------------ |
| **Ad-hoc (on-demand)**   | **Athena**                 | Run SQL directly on S3; no setup                 |
| **Batch / BI Analytics** | **Redshift**               | Large-scale warehouse; fast for repeated queries |
| **Real-time streaming**  | **Kinesis Data Analytics** | Analyze streaming data in real time              |
| **Data prep / ETL**      | **AWS Glue**               | Clean, catalog, and prepare data                 |
| **Big data processing**  | **Amazon EMR**             | Hadoop/Spark clusters for heavy data processing  |

```
Do you need to analyze data?  
│
├──> No → ❌ No analytics needed
│
└──> Yes
     │
     ├── Where is your data stored?
     │       │
     │       ├── In S3 → Continue ↓
     │       └── In a database (RDS, DynamoDB, etc.) → Use Amazon QuickSight or Export to S3
     │
     ├── Do you need real-time (streaming) analysis?
     │       │
     │       ├── Yes → ✅ Use Amazon Kinesis Data Analytics (for real-time SQL on streams)
     │       └── No → Continue ↓
     │
     ├── Is this ad-hoc or exploratory analysis? (one-time, unscheduled queries)
     │       │
     │       ├── Yes → ✅ Use Amazon Athena (serverless SQL directly on S3)
     │       └── No → Continue ↓
     │
     ├── Do you need repeated, large-scale analytics or BI dashboards?
     │       │
     │       ├── Yes → ✅ Use Amazon Redshift (data warehouse)
     │       │
     │       └── No → Continue ↓
     │
     ├── Do you need to transform or prepare data first?
     │       │
     │       ├── Yes → 🧩 Use AWS Glue for ETL → Then query with Athena or Redshift
     │       └── No → Continue ↓
     │
     └── Do you need machine learning or big data processing?
             │
             ├── Yes → 🧠 Use Amazon EMR (Spark/Hadoop) or SageMaker
             └── No → ✅ Stick with Athena or Redshift depending on workload
```


**Summary:**

* **NFS (Network File System)** is a protocol that lets you access and transfer files over a network as if they were on a local drive.
* On **AWS Snowball Edge**, NFS allows you to **mount the device** on your local server and **copy files directly** using standard file operations.
* It uses **NFSv3**, supports **AES-256 encryption**, and integrates with **AWS KMS** for key management.
* This makes it easy and secure to move large datasets to the Snowball Edge without special software.



| Service                 | Description                                                                               | Best For                                                          |
| ----------------------- | ----------------------------------------------------------------------------------------- | ----------------------------------------------------------------- |
| **AWS Snowcone**        | Small, portable (8 TB) version of Snowball Edge. Runs EC2 and Lambda locally.             | Edge computing in tight or mobile spaces (e.g. drones, vehicles). |
| **AWS Snowmobile**      | Truck-sized data transfer service (up to 100 PB per truck).                               | Massive data migrations (exabyte scale).                          |
| **AWS DataSync**        | Software-based online data transfer tool (no physical device).                            | Continuous or scheduled transfers over the internet.              |
| **AWS Transfer Family** | Provides managed FTP, FTPS, and SFTP endpoints for S3 and EFS.                            | Application-level file transfers.                                 |
| **AWS Storage Gateway** | Hybrid cloud storage connecting on-prem apps to AWS storage (file, volume, or tape mode). | Extending on-premises storage to AWS.                             |


```
Need AWS integration?
 ├─ Yes
 │   ├─ Need fan-out → SNS
 │   ├─ Need event routing/filtering → EventBridge
 │   ├─ Need message queue → SQS
 │   └─ Need stream analytics → Kinesis
 └─ No
     ├─ Need durable streaming → Kafka
     ├─ Need complex routing → RabbitMQ
     ├─ Need lightweight pub/sub → NATS
     └─ Need IoT protocol → MQTT broker

```




Let’s build a clear **decision tree (text diagram)** showing **when to choose Amazon SQS, SNS, EventBridge, Step Functions, or Kinesis** — all are “messaging or eventing” services but serve *different patterns*.

---

## 🌳 **Decision Tree: AWS Messaging & Eventing Services**

```
                      ┌──────────────────────────────┐
                      │   Do you need to send data   │
                      │   between system components? │
                      └──────────────┬───────────────┘
                                     │
                    ┌────────────────┴────────────────┐
                    │                                 │
        Real-time event routing?           Asynchronous job/work queue?
                    │                                 │
           (publish-subscribe)                (producer-consumer)
                    │                                 │
         ┌──────────┴──────────┐               ┌──────┴────────┐
         │                     │               │               │
   One-to-many fanout?     Event filtering,    High throughput?  Need job
         │                 schema, SaaS?           │             coordination?
         │                     │                   │                  │
         │                     │                   │                  │
      ┌──┴───┐           ┌─────┴─────┐        ┌────┴────┐         ┌──┴───┐
      │ SNS  │           │ EventBridge│        │ Kinesis │         │ SQS  │
      └──────┘           └────────────┘        └─────────┘         └──────┘
     Simple fanout,     Advanced event bus,   Streaming analytics,  Reliable queue
     alerts, push,      rule-based routing,   real-time pipelines,  task buffering,
     mobile/email SMS   cross-service events  custom consumers      scaling by depth
```



## 🧩 **Summary Table**

| Service                               | Communication Type        | Delivery Model        | Retention       | Ideal For                                  | Example Use Case                         |
| ------------------------------------- | ------------------------- | --------------------- | --------------- | ------------------------------------------ | ---------------------------------------- |
| **SQS (Simple Queue Service)**        | Point-to-point            | Pull (poll)           | Up to 14 days   | Decoupling producers and workers           | Job queue for EC2/Lambda workers         |
| **SNS (Simple Notification Service)** | One-to-many               | Push                  | No persistence  | Fan-out notifications                      | Send alerts to email, SMS, Lambda        |
| **EventBridge**                       | Many-to-many (Event Bus)  | Push                  | Short retention | Event-driven integrations, filtering, SaaS | Trigger workflows when S3 object created |
| **Kinesis Data Streams**              | Many-to-many (Stream)     | Pull (shard consumer) | 24h–7d          | Real-time analytics, log ingestion         | Streaming sensor or click data           |
| **Step Functions**                    | Orchestration             | State machine         | Managed state   | Workflow coordination                      | Chain Lambdas for data processing        |
| **Lambda Event Source Mapping**       | Depends (SQS/Kinesis/SNS) | Pull/Push             | —               | Auto-scale serverless consumers            | Trigger Lambda per queue or stream event |

---

## ⚙️ **How to Choose (Step-by-Step)**

1. **Do I need to handle job queues or delayed tasks?**
   → ✅ **SQS**

2. **Do I need to notify multiple subscribers simultaneously (fan-out)?**
   → ✅ **SNS**

3. **Do I need event routing between AWS services or SaaS with filtering/rules?**
   → ✅ **EventBridge**

4. **Do I need high-throughput streaming data (logs, telemetry, analytics)?**
   → ✅ **Kinesis**

5. **Do I need to orchestrate multiple tasks or services with logic?**
   → ✅ **Step Functions**

6. **Do I need real-time notifications for users (e.g., mobile, email)?**
   → ✅ **SNS (Mobile Push / Email / SMS)**

7. **Do I need to handle replay or ordered event streams?**
   → ✅ **Kinesis (or SQS FIFO for ordering)**



## 🧠 Quick Mnemonic

| Pattern                                            | Service |
| -------------------------------------------------- | ------- |
| **Notify me** → SNS                                |         |
| **Tell everyone something happened** → EventBridge |         |
| **Do this job when you can** → SQS                 |         |
| **Stream data continuously** → Kinesis             |         |
| **Run these tasks in order** → Step Functions      |         |


SMB (Server Message Block) file server là một file server sử dụng giao thức SMB để chia sẻ tệp, thư mục, và máy in qua mạng. Đây là công nghệ chủ yếu được sử dụng trong Windows environments, nhưng cũng được hỗ trợ trên Linux (Samba) và macOS.

AWS Global Accelerator (GA) is a networking service that improves availability, performance, and global reach of your applications hosted on AWS.

It works at the network layer (Layer 4 - TCP/UDP) — not the application layer like CloudFront — and uses the AWS global network (not the public internet) to route user traffic efficiently to your application endpoints.
| Feature               | **Global Accelerator**                           | **CloudFront**               |
| :-------------------- | :----------------------------------------------- | :--------------------------- |
| Layer                 | **Network (L4)**                                 | **Application (L7)**         |
| Protocol              | TCP / UDP                                        | HTTP / HTTPS                 |
| Use Case              | Low-latency access to apps (e.g., ALB, EC2, NLB) | Caching and content delivery |
| Caching               | ❌ No                                             | ✅ Yes                        |
| Static IPs            | ✅ Yes                                            | ❌ No                         |
| Traffic Type          | Dynamic or non-HTTP (gaming, API, etc.)          | Static / HTTP content        |
| Multi-region failover | ✅ Yes                                            | ⚠️ Possible, but slower      |




GuardDuty → Detects threats (no blocking).

Traffic Mirroring → For custom monitoring/IDS (manual setup).

Network Firewall → Managed inspection + filtering (recommended here).

Firewall Manager → Manages firewall rules across multiple accounts/VPCs.




Great question — let’s make it super clear 👇

---

## 🧠 What Amazon QuickSight Is

**Amazon QuickSight** is **AWS’s business intelligence (BI) and data visualization service**.
It lets you **analyze and visualize your data** from multiple AWS or external data sources — similar to **Tableau**, **Power BI**, or **Looker**.

You can use it to turn your raw data (in S3, RDS, Redshift, Athena, etc.) into **interactive dashboards, reports, and charts** that can be shared across your organization.

---

## 🔹 In Simple Terms

QuickSight =

> “A tool that helps you build dashboards and visualize data stored in AWS.”

Example:
You have:

* Sales data in **Amazon RDS for PostgreSQL**
* Website logs in **S3 (analyzed via Athena)**

With QuickSight:

* You connect to those sources.
* Create a dataset that combines them.
* Build charts like “Sales by Region”, “Traffic vs Revenue”.
* Publish dashboards for managers and teams to view.

---

## 🔹 What QuickSight Can Do

| Feature                           | Description                                                                         |
| --------------------------------- | ----------------------------------------------------------------------------------- |
| **Data Visualization**            | Create bar charts, heat maps, pie charts, KPIs, trend lines, etc.                   |
| **Interactive Dashboards**        | Users can filter, drill down, and interact with visuals.                            |
| **Data Sources**                  | Connect to AWS services (S3, Redshift, Athena, RDS) and external databases or APIs. |
| **Auto-refresh / Scheduled Data** | Automatically updates data on a schedule.                                           |
| **Sharing & Permissions**         | Share dashboards with specific users or groups; apply row-level security.           |
| **Embedded Analytics**            | You can embed dashboards into internal web apps or portals.                         |
| **Machine Learning Insights**     | Use built-in ML to detect anomalies or forecast trends.                             |

---

## 🔹 Common Use Cases

| Use Case                  | Example                                                |
| ------------------------- | ------------------------------------------------------ |
| **Business dashboards**   | Visualize sales performance, profit by product line.   |
| **Operational reporting** | Monitor system metrics, operations KPIs.               |
| **Data lake analytics**   | Analyze data in S3 + Athena + RDS without moving data. |
| **Executive dashboards**  | Provide high-level summaries for management.           |

---

## 🔹 Typical AWS Data Flow

```
       +-------------------+
       |  Amazon S3 / RDS  |
       +---------+---------+
                 |
                 ▼
        +----------------+
        |  AWS Glue /     |
        |  Athena / Redshift|
        +--------+--------+
                 |
                 ▼
         +----------------+
         | Amazon QuickSight|
         | (Visualization)  |
         +----------------+
                 |
                 ▼
        Dashboards for users
```

---

## 🔹 Why Companies Use QuickSight

✅ **Fully managed** — no server setup.
✅ **Scales automatically** — works for 10 users or 10,000.
✅ **Integrates with AWS data easily**.
✅ **Pay-per-session** pricing — you only pay when users actually view dashboards.
✅ **Secure sharing** with fine-grained access control.

---

Would you like me to show a **real-world example** (like how a company combines S3 + RDS + QuickSight for management dashboards)?
