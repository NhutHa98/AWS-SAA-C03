
## 🗄️ AWS Database Services

| Service                 | Database type                                                       | When to use                            | Emoji |
| ----------------------- | ------------------------------------------------------------------- | -------------------------------------- | ----- |
| **Amazon RDS**          | Managed relational (MySQL, PostgreSQL, MariaDB, Oracle, SQL Server) | Traditional relational apps            | 🧩    |
| **Amazon Aurora**       | Cloud-native relational (MySQL / PostgreSQL compatible)             | High performance + HA relational DB    | ⚡     |
| **ElastiCache**         | In-memory key-value (Redis, Memcached)                              | Caching, sessions, real-time data      | ⚡🧠   |
| **Amazon MemoryDB**     | Durable in-memory (Redis compatible)                                | Ultra-fast DB with persistence         | 🧠💾  |
| **DynamoDB**            | NoSQL key-value & document                                          | Serverless, massive scale, low latency | 🚀    |
| **Amazon Keyspaces**    | Wide-column (Cassandra-compatible)                                  | Cassandra workloads, serverless        | 🗂️   |
| **Amazon DocumentDB**   | Document (MongoDB-compatible)                                       | JSON-like document storage             | 📄    |
| **Amazon Neptune**      | Graph database                                                      | Relationships, fraud, recommendations  | 🕸️   |
| **Amazon Timestream**   | Time-series DB                                                      | IoT, metrics, monitoring               | ⏱️    |
| **Aurora DSQL**         | Distributed SQL (serverless)                                        | Global, strongly consistent SQL        | 🌍    |
| **Oracle Database@AWS** | Oracle DB on AWS-managed infra                                      | Oracle workloads with low latency      | 🏛️   |

---

## 🧠 Ultra-short mental model

### Relational

* **RDS** → standard
* **Aurora** → faster, scalable
* **Aurora DSQL** → global, serverless SQL

### NoSQL / Specialized

* **DynamoDB** → key-value king
* **Keyspaces** → Cassandra
* **DocumentDB** → MongoDB
* **Neptune** → graph
* **Timestream** → time-series

### In-memory

* **ElastiCache** → cache
* **MemoryDB** → real DB in memory

### Enterprise

* **Oracle Database@AWS** → Oracle without leaving AWS

---

## 🎯 Exam shortcuts (SAA-C03 style)

* **Need sub-ms latency at massive scale?** → DynamoDB
* **Need cache to reduce DB load?** → ElastiCache
* **Need relationships traversal?** → Neptune
* **Need IoT metrics over time?** → Timestream
* **Need MySQL/Postgres but faster?** → Aurora
* **Need Redis but durable?** → MemoryDB

