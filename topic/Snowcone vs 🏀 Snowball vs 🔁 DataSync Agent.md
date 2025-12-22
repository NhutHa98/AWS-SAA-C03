Love this kind of exam-brain question 😄
Let’s lock it in **fast + memorable**.

---

## 🧊 Snowcone vs 🏀 Snowball vs 🔁 DataSync Agent

| Service               | What it really is                | Typical use                        | Permissions (NTFS)        | Key exam clue                              |
| --------------------- | -------------------------------- | ---------------------------------- | ------------------------- | ------------------------------------------ |
| **🧊 Snowcone**       | *Small edge device with compute* | Remote / edge sites, low bandwidth | ✅ **Yes (with DataSync)** | “Edge”, “portable”, “run EC2/DataSync”     |
| **🏀 Snowball Edge**  | *Large data shipping appliance*  | PB/TB-scale **offline** transfer   | ❌ **No (S3 import)**      | “Ship device”, “offline”, “bulk migration” |
| **🔁 DataSync Agent** | *Online file transfer service*   | SMB/NFS → AWS storage              | ✅ **Yes**                 | “Preserve permissions”, “ongoing sync”     |

---

## 🔍 What really matters (hidden exam logic)

### Snowcone

* Can **run DataSync agent**
* Transfers data **online**
* Reads files via **SMB**
* Preserves **NTFS ACLs**

### Snowball

* Copies data → **S3**
* Offline shipping
* **No NTFS permission support**
* Designed for **bulk data**, not file servers

### DataSync agent (alone)

* Installed on:

  * On-prem server
  * VM
  * **Snowcone**
* Best for:

  * File server consolidation
  * Hybrid sync
  * Incremental updates

---

## 🧠 1-LINE EXAM ELIMINATION RULE (⭐ memorize this)

> **If NTFS permissions must be preserved → eliminate ANY option that sends data through S3**

That instantly kills:

* Snowball → S3
* Disk import → S3
* CLI copy → S3

---

## ⚡ Ultra-short decision cheat sheet

* **Need ACLs?** → ✅ DataSync
* **Edge / bad network?** → ✅ Snowcone + DataSync
* **Huge offline bulk copy?** → ❌ Snowball (no ACLs)

---

If you want next:

* 🔥 “One-glance diagram”
* 📘 Exam trick questions around Snow services
* 🧩 Real-world architecture comparison
