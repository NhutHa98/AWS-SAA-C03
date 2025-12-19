
# 🔴 Live Streaming & Real-time Video (AWS)

## 🧩 Bài toán chung

> **Nhận video → xử lý → đóng gói → phân phối → (tuỳ chọn) tương tác / quảng cáo**

```
Camera / Encoder
      ↓
MediaLive (encode)
      ↓
MediaPackage (HLS/DASH)
      ↓
CloudFront
      ↓
Viewer
        ↘ (optional)
         MediaTailor (Ads)
```

---

## 1️⃣ AWS Elemental **MediaLive** 📺

### 🎯 Vai trò: **Live video encoding & processing**

**Nó làm gì?**

* Nhận **live input** (RTMP, RTP, SRT, MediaConnect…)
* Encode thành nhiều bitrate (ABR)
* Output sang MediaPackage / S3 / MediaConnect

**Use case chuẩn**

* Live TV
* Live event (concert, sport)
* OTT platforms

**Điểm mạnh**

* Broadcast-grade
* Multi-AZ (Standard channel)
* Chuẩn công nghiệp (SMPTE, SCTE-35)

**⚠️ Không làm**

* Không phân phối trực tiếp tới người xem
* Không lưu trữ dài hạn

👉 **Nhớ nhanh**:

> *“MediaLive = encoder cho live”*

---

## 2️⃣ AWS Elemental **MediaPackage** 📦

### 🎯 Vai trò: **Packaging & Origin cho streaming**

**Nó làm gì?**

* Nhận stream từ MediaLive
* Đóng gói thành:

  * HLS
  * DASH
  * CMAF
* Là **origin** cho CloudFront

**Use case**

* Adaptive streaming
* DRM (Widevine, FairPlay, PlayReady)
* Live + VOD

**Điểm mạnh**

* Low latency
* Hỗ trợ DRM
* Không cần tự build origin server

**⚠️ Không làm**

* Không encode
* Không ingest video gốc

👉 **Nhớ nhanh**:

> *“MediaPackage = đóng gói & phát”*

---

## 3️⃣ **Amazon IVS** 🕹️

### 🎯 Vai trò: **Live streaming có tương tác, độ trễ thấp**

**Nó làm gì?**

* Live streaming managed hoàn toàn
* Có **chat, emoji, events**
* Latency ~ **1–3 giây**

**Use case**

* Game streaming
* Livestream bán hàng
* Creator platforms (giống Twitch 👀)

**Điểm mạnh**

* Không cần MediaLive + MediaPackage
* SDK sẵn (Web, iOS, Android)

**⚠️ Giới hạn**

* Không phù hợp broadcast TV
* Custom thấp hơn MediaLive stack

👉 **Nhớ nhanh**:

> *“IVS = Twitch-style live streaming”*

---

## 4️⃣ **Kinesis Video Streams** 🎥

### 🎯 Vai trò: **Ingest real-time video từ device**

**Nó làm gì?**

* Stream video từ:

  * Camera
  * IoT device
* Lưu trữ tạm & replay
* Tích hợp ML (Rekognition)

**Use case**

* CCTV
* Face recognition
* Video analytics

**⚠️ Không dùng cho**

* OTT streaming
* Live TV cho end user

👉 **Nhớ nhanh**:

> *“Kinesis Video = device → AWS (not Netflix)”*

---

## 5️⃣ **AWS Elemental MediaConnect** 🔗

### 🎯 Vai trò: **Live video transport (broadcast-grade)**

**Nó làm gì?**

* Truyền live video **độ tin cậy cao**
* Point-to-point / one-to-many
* Thay satellite / fiber truyền thống

**Use case**

* Studio → AWS
* AWS → broadcaster khác
* Sports broadcast

**Điểm mạnh**

* Secure
* Predictable latency
* Pay-as-you-go

👉 **Nhớ nhanh**:

> *“MediaConnect = cáp quang trên cloud”*

---

## 🧠 So sánh nhanh (rất hay ra thi)

| Service       | Encode | Package | Interactive | Device video | Broadcast |
| ------------- | ------ | ------- | ----------- | ------------ | --------- |
| MediaLive     | ✅      | ❌       | ❌           | ❌            | ✅         |
| MediaPackage  | ❌      | ✅       | ❌           | ❌            | ✅         |
| IVS           | ✅      | ✅       | ✅           | ❌            | ❌         |
| Kinesis Video | ❌      | ❌       | ❌           | ✅            | ❌         |
| MediaConnect  | ❌      | ❌       | ❌           | ❌            | ✅         |

---

## 🎯 Chọn service thế nào?

### 👉 Live TV / Sport / OTT

```
MediaConnect (optional)
 → MediaLive
 → MediaPackage
 → CloudFront
```

### 👉 Livestream bán hàng / game

```
Amazon IVS
```

### 👉 Camera / IoT / AI

```
Kinesis Video Streams
 → Rekognition / ML
```

---

## 📝 Exam Tips (SAA / SAP)

* ❌ **IVS ≠ MediaLive**
* ❌ **Kinesis Video ≠ streaming cho user**
* ✅ **MediaLive + MediaPackage = chuẩn OTT**
* 🔥 Từ khóa:

  * *broadcast-grade* → MediaLive / MediaConnect
  * *interactive chat* → IVS
  * *camera / IoT* → Kinesis Video

