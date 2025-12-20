## AWS OAI 
    💡 a CloudFront identity that lets only CloudFront access a private S3 bucket, blocking direct public S3 access. 

    ➡️ Secure static content by forcing users to access S3 only through CloudFront (for caching, HTTPS, WAF, geo-blocking), while blocking direct S3 access.


## AWS Transfer Family – ghi chú ngắn gọn (3 ý)

1️⃣ Định nghĩa
Dịch vụ managed cho phép truyền file vào/ra S3 hoặc EFS thông qua SFTP / FTPS / FTP mà không cần tự quản lý FTP server.

2️⃣ Use case
Dùng khi đối tác hoặc hệ thống legacy cần upload/download file bằng SFTP (kế toán, ERP, ngân hàng, media ingest, data exchange).

3️⃣ Ghi chú
	•	Không dùng để migrate dữ liệu lớn (so với DataSync)
	•	Hỗ trợ IAM, SSH key, endpoint public hoặc private (VPC)
	•	Chi phí tính theo giờ endpoint + data transfer