| Type of Analysis         | Recommended AWS Service    | Description                                      |
| ------------------------ | -------------------------- | ------------------------------------------------ |
| **Ad-hoc (on-demand)**   | **Athena**                 | Run SQL directly on S3; no setup                 |
| **Batch / BI Analytics** | **Redshift**               | Large-scale warehouse; fast for repeated queries |
| **Real-time streaming**  | **Kinesis Data Analytics** | Analyze streaming data in real time              |
| **Data prep / ETL**      | **AWS Glue**               | Clean, catalog, and prepare data                 |
| **Big data processing**  | **Amazon EMR**             | Hadoop/Spark clusters for heavy data processing  |

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


**Summary:**

* **NFS (Network File System)** is a protocol that lets you access and transfer files over a network as if they were on a local drive.
* On **AWS Snowball Edge**, NFS allows you to **mount the device** on your local server and **copy files directly** using standard file operations.
* It uses **NFSv3**, supports **AES-256 encryption**, and integrates with **AWS KMS** for key management.
* This makes it easy and secure to move large datasets to the Snowball Edge without special software.



**Summary:**

* **NFS (Network File System)** is a protocol that lets you access and transfer files over a network as if they were on a local drive.
* On **AWS Snowball Edge**, NFS allows you to **mount the device** on your local server and **copy files directly** using standard file operations.
* It uses **NFSv3**, supports **AES-256 encryption**, and integrates with **AWS KMS** for key management.
* This makes it easy and secure to move large datasets to the Snowball Edge without special software.
