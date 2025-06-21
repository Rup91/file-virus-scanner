## File Virus Scanner - CLoud-Native Architecture

This repository contains two cloud-native architecture designs for implementing virus scanning in the file upload workflows:

1. ✔ Pre-Upload Virus Scanning
2. ✔ Post-Upload Virus Scanning

Both approaches use AWS services, serverless patterns, and antivirus integration such as ClamAV.

## ⚠ Security Considerations

➡ Files are scanned in-memory: no disk persistence.

➡ Lambda functions use minimal IAM roles

➡ Quarantined files are isolated with strict permissions

## 🎯 Real-Life Applications

➡ Resume upload portals (HR tech)

➡ Document management systems

➡ Enterprise intranet portals

➡ Legal and healthcare file storage

