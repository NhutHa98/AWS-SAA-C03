

| Service                                 | What it is                                                       | When to use                          | Emoji |
| --------------------------------------- | ---------------------------------------------------------------- | ------------------------------------ | ----- |
| **Amazon S3**                           | Object storage (infinitely scalable)                             | Static files, backups, data lakes    | 🪣    |
| **Amazon EFS**                          | Managed NFS file system                                          | Shared file storage for EC2/EKS      | 📂    |
| **Amazon FSx**                          | High-performance file systems (Windows, Lustre, NetApp, OpenZFS) | Enterprise or HPC workloads          | 🚀    |
| **Amazon S3 Glacier**                   | Low-cost archival storage                                        | Long-term backup & compliance        | 🧊    |
| **AWS Storage Gateway**                 | Hybrid on-prem ↔ AWS storage                                     | Gradual cloud migration              | 🌉    |
| **AWS Backup**                          | Centralized backup service                                       | Automate backups across AWS services | 💾    |
| **Recycle Bin**                         | Recover accidentally deleted resources                           | Protection from human error          | ♻️    |
| **AWS Elastic Disaster Recovery (DRS)** | Continuous replication for fast recovery                         | DR with low RPO/RTO                  | 🛟    |

**Super-fast mental model 🧠**

* **S3** = objects
* **EFS / FSx** = files
* **Glacier** = archive
* **Storage Gateway** = hybrid bridge
* **Backup / Recycle Bin** = safety nets
* **DRS** = disaster recovery


