✅ Correct answer:
[x] If you use production online transaction processing (OLTP) workloads.

Explanation:

You should choose Provisioned IOPS (Input/Output Operations Per Second) for Amazon RDS when your workloads require high, consistent, and low-latency I/O performance — typically in production OLTP systems such as financial, e-commerce, or ERP databases.

| Storage Type                   | Description                                                              | Best for                                                            |
| ------------------------------ | ------------------------------------------------------------------------ | ------------------------------------------------------------------- |
| **Provisioned IOPS (io1/io2)** | You specify the IOPS rate; offers consistent and predictable performance | **Production OLTP workloads**, mission-critical databases           |
| **General Purpose (gp2/gp3)**  | Balances price and performance; bursts allowed                           | Development, testing, or moderate workloads                         |
| **Magnetic (standard)**        | Legacy option; lowest cost but inconsistent performance                  | **Batch workloads** or archival data, **not performance-sensitive** |


So:

❌ Batch-oriented workloads → Use Standard or General Purpose SSD, not Provisioned IOPS.

✅ Production OLTP workloads → Use Provisioned IOPS.

❌ Workloads not sensitive to consistent performance → Don’t need Provisioned IOPS.


| Thuật ngữ                            | Dịch vụ         | Chức năng chính                             | Mục đích sử dụng                            |
| ------------------------------------ | --------------- | ------------------------------------------- | ------------------------------------------- |
| **RRS (Reduced Redundancy Storage)** | Amazon S3       | Lưu trữ giá rẻ, độ bền thấp                 | Cho dữ liệu có thể tái tạo (PDF, CSV)       |
| **EMR (Elastic MapReduce)**          | Amazon EMR      | Xử lý dữ liệu lớn (Big Data, Hadoop, Spark) | Sinh báo cáo, xử lý log hàng ngày           |
| **Reserved Instance (Redshift)**     | Amazon Redshift | Kho dữ liệu phân tích (data warehouse)      | Giảm chi phí cho workload chạy thường xuyên |
