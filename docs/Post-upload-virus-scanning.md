## 2. ✔ Post-Upload Virus Scanning - Architecture

### ✔ Use Case

This pattern is suited for asynchronous processing, where the file is uploaded first and scanned later in the background. This ensured faster user experience at upload time, while still maintaining file safely.

It's commonly used when:

➡ Upload speed is more important than real-time scanning.
➡ Files are stored temporarity before final processing.
➡ You want to batch scan files or use event-driven workflows

### 🎯 Components

🖍 User/Client -> Upload initiator (Web/mobile)
🖍 S3 Bucket (Upload) -> Initial storage for uploaded files
🖍 S3 Event Trigger -> Triggers Lambda on file Upload
🖍 Lambda function -> Executes virus scanning logic
🖍 AV Enginer -> ClamAV or commercial AV integration - for scans file content
🖍 Decision Node -> Routes clean or infected files
🖍 Clean S3 Bucket -> Storage for clean/verified files only.
🖍 Quarantine Bucket -> For infected or suspicious files

### 📌 Flow

1️⃣ User uploads file directly to S3
2️⃣ S3 trigger Lambda function
3️⃣ Lambda scans file using ClamAV
4️⃣ If clean -> moves to Clean Bucket
5️⃣ If infected -> rejected and error returned to client and moves to quarantine bucket.