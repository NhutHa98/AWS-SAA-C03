
## 🔴 Live Streaming & Real-time Video

> Phát video **trực tiếp**, độ trễ thấp

| Dịch vụ                      | Định nghĩa                           | Use case                           | Ghi chú                      |
| ---------------------------- | ------------------------------------ | ---------------------------------- | ---------------------------- |
| 📺 **MediaLive**             | Xử lý & encode live video            | Truyền hình trực tiếp, live event  | Kết hợp MediaPackage         |
| 📦 **MediaPackage**          | Đóng gói live/VOD (HLS, DASH)        | Adaptive bitrate streaming         | Không encode                 |
| 🕹️ **Amazon IVS**           | Live interactive streaming           | Game streaming, livestream có chat | Low latency (~2s)            |
| 🎥 **Kinesis Video Streams** | Stream video real-time từ device     | Camera, IoT, ML vision             | Không dành cho OTT streaming |
| 🔗 **MediaConnect**          | Truyền tải live video chất lượng cao | Studio → AWS / Partner             | Reliable, broadcast-grade    |

---

## 🟡 Video Processing / Transcoding (File-based)

> Xử lý **video file**, không phải live

| Dịch vụ                                 | Định nghĩa               | Use case               | Ghi chú                     |
| --------------------------------------- | ------------------------ | ---------------------- | --------------------------- |
| 🎬 **MediaConvert**                     | File-based transcoding   | VOD platforms          | Thay thế Elastic Transcoder |
| 🔄 **Elastic Transcoder**               | Transcoding video legacy | Convert video cũ       | Legacy ⚠️                   |
| 🖥️ **Elemental Appliances & Software** | Encode/transcode on-prem | Broadcaster enterprise | Hybrid cloud                |

---

## 🟢 Media Storage (Low-latency)

> Lưu trữ video cho streaming

| Dịch vụ            | Định nghĩa               | Use case              | Ghi chú            |
| ------------------ | ------------------------ | --------------------- | ------------------ |
| 🗄️ **MediaStore** | Storage tối ưu cho media | Live streaming origin | Low latency hơn S3 |

---

## 🔵 Advertising & Monetization

> Kiếm tiền từ video

| Dịch vụ            | Định nghĩa               | Use case                | Ghi chú           |
| ------------------ | ------------------------ | ----------------------- | ----------------- |
| 🎯 **MediaTailor** | Server-side ad insertion | Chèn quảng cáo live/VOD | Không bị ad-block |

---

## 🟣 Rendering / Media Production

> Dựng phim, VFX, animation

| Dịch vụ                    | Định nghĩa             | Use case           | Ghi chú                    |
| -------------------------- | ---------------------- | ------------------ | -------------------------- |
| 🎞️ **AWS Deadline Cloud** | Render farm management | VFX, 3D, animation | Trước là Thinkbox Deadline |

---

## 🧠 Ghi nhớ nhanh (exam tip)

```
🎥 Capture      → Kinesis Video Streams
📺 Live Encode  → MediaLive
📦 Package      → MediaPackage
🎯 Ads          → MediaTailor
🔗 Transport    → MediaConnect
🎬 File Encode  → MediaConvert
🗄️ Origin       → MediaStore
🕹️ Interactive → IVS
🎞️ Render       → Deadline Cloud
