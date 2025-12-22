
## 🔹 AWS App Mesh

**1️⃣ Định nghĩa**

* **Service mesh** managed service trên AWS.
* Giúp **giám sát, kết nối, và bảo mật các microservices**.
* Hoạt động trên **EC2, ECS, EKS** hoặc on-prem có thể kết nối qua **App Mesh Envoy proxy**.

**2️⃣ Chức năng chính**

* **Traffic routing**: điều hướng request giữa microservices (canary, blue/green).
* **Observability**: metrics, logs, tracing (CloudWatch, X-Ray).
* **Security**: TLS giữa services, authentication & authorization.
* **Resiliency**: retry, failover, circuit breaker.

**3️⃣ Use case điển hình**

* Microservices architecture: cần kết nối nhiều service, đảm bảo **reliability & security**.
* Triển khai **canary deployment** hoặc **traffic splitting**.
* Giám sát service-to-service traffic và debugging.

**4️⃣ Khác với ALB / API Gateway**

| Chức năng | AWS App Mesh           | ALB / API Gateway         |
| --------- | ---------------------- | ------------------------- |
| Layer     | L7 service-to-service  | L7/L4 external traffic    |
| Focus     | Microservices internal | Public API / HTTP routing |
| Security  | TLS giữa service       | HTTPS/TLS external client |
| Routing   | Service-to-service     | Client → Service          |

---

💡 **Tip SAA:**

* Nếu câu hỏi đề cập đến **“microservices, internal service-to-service communication, traffic routing, TLS, observability”** → App Mesh.
* **Không dùng App Mesh** cho: static website, public API, hoặc caching – những trường hợp này dùng **CloudFront, API Gateway, ELB**.


