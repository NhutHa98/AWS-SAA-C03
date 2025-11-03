Here’s a **clean, compact summary** of our chat session 👇

---

## 🧠 **Scenario Recap**

A company uses **Amazon DynamoDB** to store customer data.
They need a disaster recovery plan that meets:

* **RPO (Recovery Point Objective)** = **15 minutes**
* **RTO (Recovery Time Objective)** = **1 hour**

The architect must choose a design that minimizes data loss (RPO) and recovery delay (RTO).

---

## 🔑 **Key Concepts Explained**

| Term                               | Meaning                                                                                         | Example                                                               |
| ---------------------------------- | ----------------------------------------------------------------------------------------------- | --------------------------------------------------------------------- |
| **RPO (Recovery Point Objective)** | The **maximum acceptable data loss** in time.                                                   | RPO = 15 min → You can lose at most 15 minutes of data.               |
| **RTO (Recovery Time Objective)**  | The **maximum acceptable downtime** to restore service.                                         | RTO = 1 hr → System must be back online within 1 hour.                |
| **PITR (Point-in-Time Recovery)**  | DynamoDB’s **continuous backup** feature that allows restore to any second in the past 35 days. | Roll back your table to 14 min before a data corruption.              |
| **On-Demand Backup**               | A **manual snapshot** of the whole table, triggered when you choose.                            | Take a backup before a major deployment.                              |
| **S3 Export**                      | Export DynamoDB data to **Amazon S3** for long-term backup or analytics.                        | Hourly or daily export to S3 for archive.                             |
| **Global Table**                   | **Multi-Region replication** for high availability and regional disaster recovery.              | If `us-east-1` fails, traffic automatically goes to `ap-southeast-1`. |
| **DynamoDB Streams (CDC)**         | Stream of item-level changes that can be used for **custom backups or analytics**.              | Push all updates to S3 for real-time logging.                         |

---

## ⚙️ **Backup & Recovery Options Comparison**

| Option                            | Type                     | Protects Against                    | RPO                     | RTO         | Pros                           | Cons                                    |
| --------------------------------- | ------------------------ | ----------------------------------- | ----------------------- | ----------- | ------------------------------ | --------------------------------------- |
| **PITR (Point-in-Time Recovery)** | Continuous               | Data corruption, accidental deletes | ⏱️ Seconds (≤15 min)    | 🕐 ~1 hr    | Fully managed, precise restore | No regional redundancy                  |
| **On-Demand Backup**              | Manual / Scheduled       | Data corruption                     | ⏱️ Depends on frequency | 🕐 ~1 hr    | Easy to trigger, durable       | No automatic protection between backups |
| **Export to S3**                  | Batch                    | Data corruption, archive            | ⏱️ ≥1 hr                | 🕐 >1 hr    | Low-cost long-term backup      | Manual restore, slow                    |
| **Global Tables**                 | Multi-Region Replication | Region outage                       | ⚡ Near-zero             | ⚡ Seconds   | Automatic region failover      | Corruption replicates instantly         |
| **Streams (Change Data Capture)** | Real-time log stream     | Data corruption                     | ⏱️ Seconds–minutes      | 🕐 Variable | Fine control, audit trail      | Complex to build/restore                |

---

## ✅ **Recommended Solution**

**→ Use DynamoDB Point-in-Time Recovery (PITR)**

* Meets **RPO 15 min** (continuous backup granularity).
* Meets **RTO 1 hr** (managed restore speed).
* Simplest and most reliable for **logical corruption** (accidental writes/deletes).

**Optionally combine with:**

* **Global Tables** → for multi-region disaster recovery (region outage).
* **On-Demand Backups / S3 Export** → for compliance or long-term archival.

---

**In short:**

> 🔒 **PITR = Best for fast, precise data recovery**
> 🌍 **Global Tables = Best for regional availability**
> 🪣 **S3 / Manual Backups = Best for archival & compliance**
