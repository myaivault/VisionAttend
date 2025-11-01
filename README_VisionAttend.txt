# VisionAttend

**AI-Powered Automated Attendance System using Google Workspace and n8n**

VisionAttend is a cloud-based smart attendance management solution that integrates Google Drive, Google Sheets, n8n, and a Flask-based AI backend. 
It detects student faces from classroom photos, marks attendance in real time, and automatically notifies parents of absentees.

## 🚀 Features
- Facial recognition for automatic attendance
- Google Drive integration for class photo uploads
- Google Sheets synchronization for student records
- AI-powered backend using DeepFace (Facenet)
- Gmail automation for parent notifications
- Fully automated and cloud-compatible

## 🧠 Architecture
1. Google Drive Trigger detects new photos.
2. n8n workflow sends metadata to Flask backend.
3. Flask backend identifies students using DeepFace.
4. Google Sheets is updated with attendance results.
5. Gmail node sends notifications to parents.

## 🛠️ Setup Guide

### Requirements
- Google Drive, Sheets, and Gmail accounts
- n8n instance (self-hosted or Render/Cloud)
- Flask and Python (3.10+)
- Cloudflare Tunnel or ngrok for API exposure

### Backend Setup (Google Colab)
```bash
pip install flask deepface gspread google-auth numpy
python app.py
cloudflared tunnel --url http://localhost:5000
```

### n8n Workflow Setup
- Import workflow.json to n8n
- Configure Google credentials
- Replace API URL with your public endpoint

## 🧩 Tech Stack
| Component | Technology |
|------------|-------------|
| Automation | n8n |
| Cloud Storage | Google Drive |
| Data | Google Sheets |
| Backend | Flask (Python) |
| AI Model | DeepFace (Facenet) |
| Notifications | Gmail API |
| Hosting | Google Colab + Cloudflare |

## 📈 Example Flow
1. Teacher uploads `class1.jpg`
2. n8n sends photo to backend
3. Flask matches faces → updates Google Sheet
4. Absent parents receive emails

## 📄 License
Licensed under the MIT License - see LICENSE file for details.
