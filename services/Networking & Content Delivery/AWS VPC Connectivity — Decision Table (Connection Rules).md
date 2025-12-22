

## 🧭 AWS VPC Connectivity — Decision Table (Connection Rules)

### 🔗 Connectivity Method vs Rules

| Connectivity                 | Same VPC | Same Region | Cross Region | Routing Needed | SG Reference Allowed | IP/CIDR Required | Notes / When to Use        |
| ---------------------------- | -------- | ----------- | ------------ | -------------- | -------------------- | ---------------- | -------------------------- |
| **Security Group only**      | ✅        | ❌           | ❌            | ❌              | ✅                    | ❌                | Intra-VPC or ALB → EC2     |
| **VPC Peering**              | ❌        | ✅           | ✅            | ✅              | ✅ (same Region only) | ✅ (cross-Region) | Simple 1-to-1 VPC link     |
| **Transit Gateway**          | ❌        | ✅           | ✅            | ✅              | ❌                    | ✅                | Hub-and-spoke, many VPCs   |
| **Site-to-Site VPN**         | ❌        | ✅           | ✅            | ✅              | ❌                    | ✅                | Encrypted over internet    |
| **Client VPN**               | ❌        | ✅           | ❌            | ✅              | ❌                    | ✅                | User → VPC access          |
| **Direct Connect**           | ❌        | ✅           | ✅            | ✅              | ❌                    | ✅                | Dedicated private link     |
| **PrivateLink**              | ❌        | ✅           | ❌            | ❌              | ❌                    | ❌                | Service access, no CIDRs   |
| **Internet Gateway**         | ❌        | ✅           | ✅            | ✅              | ❌                    | ✅                | Public internet traffic    |
| **NAT Gateway**              | ❌        | ✅           | ❌            | ✅              | ❌                    | ❌                | Outbound-only internet     |
| **VPC Endpoint (Gateway)**   | ❌        | ✅           | ❌            | ❌              | ❌                    | ❌                | S3 / DynamoDB only         |
| **VPC Endpoint (Interface)** | ❌        | ✅           | ❌            | ❌              | ❌                    | ❌                | Private AWS service access |

---

## 🔐 Security Group Rules — What’s Allowed?

| Scenario               | SG Reference | IP Allowed | Why                       |
| ---------------------- | ------------ | ---------- | ------------------------- |
| Same VPC               | ✅            | ✅          | Full trust boundary       |
| Peering (same Region)  | ✅            | ✅          | AWS supports SG reference |
| Peering (cross Region) | ❌            | ✅          | Region isolation          |
| Transit Gateway        | ❌            | ✅          | No SG awareness           |
| VPN / DX               | ❌            | ✅          | External networks         |
| Internet traffic       | ❌            | ✅          | Public IPs only           |
| PrivateLink            | ❌            | ❌          | ENI-based access          |

---

## 🧠 Exam Trap Quick Hits (🔥 memorize these)

* ❌ **Cross-Region SG reference = NEVER**
* ❌ **Transit Gateway = no SG reference**
* ✅ **VPC Peering = simplest**
* ✅ **TGW = scale**
* ✅ **PrivateLink = service exposure, not full network**
* ❌ **NACL = stateless**
* ❌ **SG = no deny rules**

---

## 🏆 Ultra-Short Decision Cheat Sheet

```
Need full VPC ↔ VPC?
  → Peering (few) | TGW (many)

Need cross-Region?
  → Peering or TGW (IP-based rules)

Need private AWS service access?
  → PrivateLink

Need on-prem?
  → VPN | Direct Connect
```

