## 1. ✔ Pre-Upload Virus Scanning - Architecture

### ✔ Use Case

This approach is ideal when security is critical before storing any user-generated content. The file is scanned in real-time before it's accepted and saved to cloud storage.

➡ It's commonly from untrusted sources.
➡ Immediate validation is required.
➡ You want to block malicious uploads at the edge before consuming any backend or storage resources.
➡ This ensures only clean files are stored.

### 🎯 Components

🖍 User/Client -> Upload initiator (Web/mobile)
🖍 Frontend App -> React/Angular frontend
🖍 Virus Scan API -> Serverless API (AWS Lambda + API Gateway)
🖍 AV Enginer -> ClamAV or commercial AV integration
🖍 S3 Bucket -> Storage for clean files only.

### 📌 Flow

1️⃣ User selects a file
2️⃣ File sent to Virus Scan API
3️⃣ API scans the file using AV Engine
4️⃣ If clean -> uploads to s3
5️⃣ If infected -> rejected and error returned to client.