
## 🧩 **1. Thông tin cơ bản (Basic Info)**

| Thuộc tính        | Mô tả                                                        |
| ----------------- | ------------------------------------------------------------ |
| **AMI ID**        | Mã định danh duy nhất, ví dụ: `ami-0a12345b6c789d123`        |
| **Name**          | Tên dễ đọc bạn đặt cho AMI                                   |
| **Description**   | Mô tả về mục đích hoặc nội dung của AMI                      |
| **Owner**         | Tài khoản AWS tạo hoặc sở hữu AMI                            |
| **Creation date** | Thời điểm AMI được tạo                                       |
| **Platform**      | Hệ điều hành (Windows, Linux, Ubuntu, RHEL, Amazon Linux...) |

---

## 💾 **2. Root Device & Storage Configuration**

| Thuộc tính                | Mô tả                                                                                                 |
| ------------------------- | ----------------------------------------------------------------------------------------------------- |
| **Root device type**      | Loại thiết bị gốc: <br>🔹 `ebs` – ổ đĩa EBS <br>🔹 `instance-store` – lưu trên ổ tạm thời (ephemeral) |
| **Root device name**      | Ví dụ `/dev/sda1`, chỉ định ổ đĩa chính                                                               |
| **Block device mappings** | Danh sách các EBS volumes hoặc instance-store volumes gắn với AMI                                     |
| **Virtualization type**   | Cách ảo hóa: `hvm` (modern) hoặc `paravirtual` (cũ hơn)                                               |
| **Architecture**          | `x86_64` hoặc `arm64` (tùy CPU)                                                                       |

---

## 🔐 **3. Encryption & KMS Integration**

| Thuộc tính       | Mô tả                                                                 |
| ---------------- | --------------------------------------------------------------------- |
| **Encrypted**    | AMI (EBS snapshots) có được mã hóa không                              |
| **KMS Key ID**   | ARN của customer-managed KMS key dùng để mã hóa snapshot              |
| **Snapshot IDs** | Liên kết đến các snapshot dùng để tạo EBS volumes khi launch instance |

---

## 🔄 **4. Permissions & Sharing Settings**

| Thuộc tính           | Mô tả                                                                                               |
| -------------------- | --------------------------------------------------------------------------------------------------- |
| **launchPermission** | Danh sách tài khoản AWS được phép “launch” AMI này <br>👉 dùng để chia sẻ AMI (public hoặc private) |
| **productCodes**     | Dùng khi AMI là phần mềm thương mại trên AWS Marketplace                                            |
| **Public**           | Boolean (`true/false`) — có công khai AMI cho mọi người không                                       |
| **OwnerAlias**       | Nếu AMI là public, hiển thị chủ sở hữu (vd: “amazon”)                                               |

---

## ⚙️ **5. Metadata & Tags**

| Thuộc tính          | Mô tả                                                            |
| ------------------- | ---------------------------------------------------------------- |
| **Tags**            | Cặp key-value gắn với AMI để quản lý (ví dụ: `Environment=Prod`) |
| **ImageType**       | Loại hình ảnh (vd: `machine`, `kernel`, `ramdisk`)               |
| **State**           | `available`, `pending`, `failed`                                 |
| **DeprecationTime** | Thời điểm AMI bị đánh dấu ngừng sử dụng (deprecated)             |

---

## 🧠 **Tóm tắt dễ nhớ**

> Một **AMI** là **mẫu hoàn chỉnh của máy chủ EC2**, gồm 4 nhóm thông tin chính:
> 🏷️ Thông tin mô tả
> 💾 Cấu hình lưu trữ
> 🔐 Bảo mật và mã hóa
> ⚙️ Quyền chia sẻ và metadata

