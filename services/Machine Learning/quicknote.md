

## 🧠 **Machine Learning & AI Services – Quick Comparison**

### 🤖 **ML Platform & Foundation Models**

| Dịch vụ                    | Định nghĩa                                         | Use case                       | Ghi chú                           |
| -------------------------- | -------------------------------------------------- | ------------------------------ | --------------------------------- |
| 🧠 **Amazon SageMaker AI** | Nền tảng build, train, deploy ML model             | Train custom ML, MLOps         | Full-stack ML, cho data scientist |
| 🧱 **Amazon Bedrock**      | Truy cập Foundation Models (Claude, Llama, Titan…) | GenAI, chatbot, text/image gen | Serverless, không cần train       |
| 🧩 **Bedrock AgentCore**   | Tạo AI Agent có workflow & tools                   | Agent tự động xử lý nghiệp vụ  | Orchestration cho GenAI           |
| 🧠 **Amazon Nova Act**     | AI cho hành động (action-based AI)                 | Tự động thao tác hệ thống      | Mới, hướng autonomous AI          |

---

### 🧑‍💼 **AI Assistant & Business AI**

| Dịch vụ                  | Định nghĩa                      | Use case                     | Ghi chú                            |
| ------------------------ | ------------------------------- | ---------------------------- | ---------------------------------- |
| 💬 **Amazon Q**          | AI assistant cho dev & AWS      | Hỏi code, AWS, infra         | GenAI cho developer                |
| 🏢 **Amazon Q Business** | AI assistant cho dữ liệu nội bộ | Search tài liệu, FAQ công ty | Kết nối S3, Confluence, SharePoint |
| 🔍 **Amazon Kendra**     | Intelligent search              | Enterprise search            | Semantic search, ranking mạnh      |

---

### 🧠 **NLP – Text Intelligence**

| Dịch vụ                   | Định nghĩa            | Use case                 | Ghi chú                |
| ------------------------- | --------------------- | ------------------------ | ---------------------- |
| 📚 **Amazon Comprehend**  | NLP phân tích văn bản | Sentiment, entity, topic | Không cần ML knowledge |
| 🏥 **Comprehend Medical** | NLP cho dữ liệu y tế  | Medical notes, ICD codes | HIPAA-friendly         |
| 🌍 **Amazon Translate**   | Dịch ngôn ngữ         | Multi-language app       | Real-time & batch      |
| 🎤 **Amazon Transcribe**  | Speech-to-text        | Subtitle, call center    | Streaming & batch      |
| 🗣 **Amazon Polly**       | Text-to-speech        | Voice bot, audiobook     | Neural voices          |

---

### 👁 **Computer Vision & Document AI**

| Dịch vụ                   | Định nghĩa               | Use case                | Ghi chú           |
| ------------------------- | ------------------------ | ----------------------- | ----------------- |
| 👁 **Amazon Rekognition** | Phân tích hình ảnh/video | Face detect, moderation | Video & Image     |
| 📄 **Amazon Textract**    | OCR + hiểu form          | Invoice, hợp đồng       | Table & key-value |
| 📷 **AWS Panorama**       | CV on-prem camera        | Smart factory, retail   | Edge AI           |

---

### 🎯 **Recommendation, Prediction & Decision**

| Dịch vụ                             | Định nghĩa              | Use case               | Ghi chú              |
| ----------------------------------- | ----------------------- | ---------------------- | -------------------- |
| 🎯 **Amazon Personalize**           | Recommendation engine   | E-commerce, media      | Giống Netflix/Amazon |
| 📈 **Amazon Forecast**              | Time-series forecasting | Demand, sales forecast | AutoML               |
| 🕵️ **Amazon Fraud Detector**       | Fraud detection         | Payment, signup fraud  | Rule + ML            |
| ⚠️ **Amazon Lookout for Equipment** | Predictive maintenance  | Máy móc, IoT           | Detect anomaly       |

---

### 🏭 **Industrial, IoT & Healthcare AI**

| Dịch vụ                  | Định nghĩa               | Use case                | Ghi chú               |
| ------------------------ | ------------------------ | ----------------------- | --------------------- |
| 🏭 **Amazon Monitron**   | ML cho công nghiệp       | Vibration & temp sensor | Plug-and-play         |
| 🧬 **AWS HealthOmics**   | Phân tích genomic        | Bioinformatics          | Dành cho life science |
| 🏥 **AWS HealthLake**    | Data lake y tế           | FHIR healthcare data    | Chuẩn y tế            |
| 🩻 **AWS HealthImaging** | Lưu & phân tích ảnh y tế | DICOM imaging           | Radiology             |

---

### 🧠 **Human-in-the-loop & Dev AI**

| Dịch vụ                             | Định nghĩa          | Use case             | Ghi chú           |
| ----------------------------------- | ------------------- | -------------------- | ----------------- |
| 🧑‍⚖️ **Amazon Augmented AI (A2I)** | Human review cho ML | Validate prediction  | ML + con người    |
| 🧑‍💻 **Amazon CodeGuru**           | AI review code      | Detect bug, optimize | Java, Python      |
| 🔧 **Amazon DevOps Guru**           | AI cho ops          | Detect infra issue   | ML cho CloudWatch |

---

### 🗣 **Conversational AI**

| Dịch vụ           | Định nghĩa    | Use case             | Ghi chú      |
| ----------------- | ------------- | -------------------- | ------------ |
| 🤖 **Amazon Lex** | Build chatbot | Customer support bot | Voice + text |

---

## 🧭 **Cách chọn nhanh (TL;DR)**

* 🤖 **Build ML từ đầu** → SageMaker
* 🧱 **GenAI nhanh gọn** → Bedrock + Q
* 📚 **Text / NLP** → Comprehend / Transcribe / Translate
* 👁 **Image / OCR** → Rekognition / Textract
* 🎯 **Recommendation / Forecast** → Personalize / Forecast
* 🏥 **Healthcare** → HealthLake / HealthImaging / HealthOmics
* 🏭 **Industrial IoT** → Monitron / Lookout for Equipment
