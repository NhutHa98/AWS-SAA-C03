
## 1️⃣ IAM Role là gì?

* **Định nghĩa:** IAM Role là một **entity trong AWS** giống như user, nhưng **không gắn trực tiếp với một người hay dịch vụ**. Thay vào đó, một role được **assume** (đảm nhận) tạm thời bởi user, service, hoặc account khác để thực hiện một số hành động.
* **Key point:** Role **cung cấp quyền**, nhưng không có credential lâu dài như IAM User.

**Ví dụ:**

* EC2 instance muốn truy cập S3. Bạn tạo một **EC2 role** có quyền đọc ghi S3, rồi gán role này cho instance. EC2 sẽ “assume” role đó để sử dụng quyền tạm thời.

---

## 2️⃣ Trusted Policy (Trust Relationship)

* **Định nghĩa:** Là chính sách xác định **ai hoặc gì có thể assume role**. Nó giống như **ai được phép mặc bộ quần áo role này**.
* **Vị trí:** Được gắn trực tiếp vào IAM Role (Role Trust Policy).
* **Ngôn ngữ:** JSON với `"Principal"` chỉ định entity nào có thể assume role.

**Ví dụ:**

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": { "Service": "ec2.amazonaws.com" },
      "Action": "sts:AssumeRole"
    }
  ]
}
```

* Đây nghĩa là **EC2 instances** có thể assume role này.
* Nếu bạn muốn cho **một user trong account khác** assume role, `"Principal"` sẽ là dạng `"AWS": "arn:aws:iam::123456789012:user/Alice"`.

---

## 3️⃣ Permission Policy (Inline hoặc Managed Policy)

* **Định nghĩa:** Là chính sách xác định **role có thể làm gì khi đã được assume**. Đây là **quyền thực sự**, kiểu “role được phép thao tác gì”.
* **Vị trí:** Gắn trực tiếp hoặc thông qua Managed Policy.
* **Ngôn ngữ:** JSON với `"Action"` và `"Resource"`.

**Ví dụ:**

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": ["s3:GetObject", "s3:PutObject"],
      "Resource": "arn:aws:s3:::my-bucket/*"
    }
  ]
}
```

* Role này có thể đọc/ghi tất cả object trong bucket `my-bucket`.

---

## 4️⃣ Tóm tắt so sánh

| Khái niệm         | Mục đích                     | Ví dụ                                 |
| ----------------- | ---------------------------- | ------------------------------------- |
| IAM Role          | Entity tạm thời, được assume | EC2Role, LambdaRole                   |
| Trusted Policy    | Ai có thể assume role        | EC2, Lambda, IAM User từ account khác |
| Permission Policy | Role có thể làm gì           | S3 read/write, DynamoDB query         |

**Analogy:**

* **Role** = bộ đồng phục
* **Trusted Policy** = ai được phép mặc đồng phục
* **Permission Policy** = những gì người mặc đồng phục có thể làm

