# Recovery & Backup (AWS)

A concise, exam‑ready and practical cheat sheet for **backup, restore, and disaster recovery** on AWS.

---

## 🎯 Goals & Terms

* **Backup**: Copy data so you can restore it later
* **Recovery**: Get systems back after failure
* **RPO** (Recovery Point Objective): How much data you can lose
* **RTO** (Recovery Time Objective): How fast you must recover

---

## 💾 Core Backup Services

### AWS Backup

* Centralized backup across AWS services
* Policy-based, scheduled, automated
* Supports: **EBS, RDS/Aurora, DynamoDB, EFS, FSx, EC2, Storage Gateway**
* Cross‑account & cross‑region copy

**Use when**: One place to manage backups at scale

---

### Amazon S3 (Backups & Archive)

* **Versioning**: Protects against overwrites/deletes
* **Lifecycle rules**: Move data to IA/Glacier/Deep Archive
* **Object Lock (WORM)**: Compliance & ransomware protection

**Use when**: Durable, low‑cost backup storage

---

### Amazon S3 Glacier Family

* **Instant Retrieval**: ms access for rare reads
* **Flexible Retrieval**: minutes–hours
* **Deep Archive**: 12–48 hours, cheapest

**Use when**: Long‑term retention & compliance

---

### Recycle Bin

* Recover accidentally deleted **EBS snapshots** and **AMIs**
* Time‑based retention

**Use when**: Human‑error protection

---

## 🛟 Disaster Recovery Services

### AWS Elastic Disaster Recovery (DRS)

* Continuous block‑level replication
* Low **RPO (seconds)**, low **RTO (minutes)**
* Works for on‑prem & cloud servers

**Use when**: Fast recovery for critical workloads

---

### Pilot Light / Warm Standby / Active‑Active

| Strategy             | Cost | RTO           | Description                   |
| -------------------- | ---- | ------------- | ----------------------------- |
| **Backup & Restore** | $    | Hours–Days    | Restore from backups          |
| **Pilot Light**      | $$   | Minutes–Hours | Minimal core running          |
| **Warm Standby**     | $$$  | Minutes       | Scaled‑down prod always on    |
| **Active‑Active**    | $$$$ | Seconds       | Full prod in multiple regions |

---

## 🧱 Database‑Specific Backup & Recovery

### RDS / Aurora

* Automated backups (PITR)
* Manual snapshots
* Multi‑AZ for HA (not backup)

### DynamoDB

* On‑demand backups
* Point‑in‑time recovery (35 days)
* Global tables for DR

### EBS

* Incremental snapshots
* Cross‑region copy

---

## 🔐 Security & Ransomware Protection

* **S3 Object Lock** (Compliance / Governance)
* **IAM least privilege**
* **MFA Delete** (S3)
* **Cross‑account backups**

---

## 🧠 Exam Traps & Tips

* Multi‑AZ ≠ Backup (it’s HA)
* Snapshots ≠ Live replication
* Glacier ≠ real‑time restore
* DRS ≠ backup (it’s recovery)

---

## ✅ Quick Decision Guide

* **Centralized backups?** → AWS Backup
* **Fast DR (minutes)?** → Elastic DRS
* **Compliance archive (years)?** → S3 Glacier Deep Archive
* **Accidental delete protection?** → Recycle Bin + Versioning

---

*Best used with lifecycle policies + cross‑region copy for full resilience.*
