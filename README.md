# 🛡️ Network Intrusion Detection System (NIDS) Using Machine Learning

A production-oriented **Network Intrusion Detection System** that combines network traffic analysis with machine learning to identify and classify suspicious activities in real time.

Built with a focus on **software engineering practices, modular architecture, data processing pipelines, and scalable ML deployment**.

---

## 🚀 Project Overview

Modern networks generate massive amounts of traffic, making manual monitoring inefficient. This project provides an intelligent detection system that analyzes network packets, extracts meaningful features, and predicts potential cyber threats using machine learning models.

The system is designed to demonstrate practical skills in:

* Backend development
* Machine learning integration
* Data preprocessing pipelines
* Network security concepts
* API development
* Software architecture

---

## ✨ Key Features

### 🔍 Real-Time Network Monitoring

* Captures live network packets using packet analysis libraries.
* Extracts important network-level information.
* Enables continuous traffic inspection.

### 🤖 Machine Learning Threat Detection

* Processes network traffic features.
* Uses trained ML models for attack classification.
* Supports model serialization and deployment.

### 🌐 Web-Based Dashboard

* Flask-powered backend application.
* Provides an interface for monitoring detection results.
* Modular route-based application structure.

### 📊 Data Analysis & Visualization

* Data preprocessing using Pandas.
* Visualization using Matplotlib and Seaborn.
* Helps analyze traffic patterns and model performance.

---

## 🏗️ System Architecture

```
Network Traffic
        |
        ↓
Packet Capture Layer
        |
        ↓
Feature Extraction
        |
        ↓
Data Processing Pipeline
        |
        ↓
Machine Learning Model
        |
        ↓
Prediction Engine
        |
        ↓
Flask Web Application
        |
        ↓
User Dashboard
```

---

## 🛠️ Tech Stack

### Backend

* Python
* Flask

### Machine Learning

* Scikit-learn
* Joblib

### Network Analysis

* Scapy
* PyShark

### Data Processing

* Pandas
* NumPy

### Visualization

* Matplotlib
* Seaborn

### Development Tools

* Git
* Virtual Environment

---

## 📂 Project Structure

```
Network_Intrusion_Detection_System/
│
├── app/
│   ├── routes.py
│   └── ...
│
├── models/
│   └── trained_model files
│
├── dataset/
│
├── static/
│
├── templates/
│
├── run.py
├── requirements.txt
├── README.md
└── .gitignore
```

---

## ⚙️ Installation & Setup

Clone the repository:

```bash
git clone https://github.com/Chintucharan/Network_Intrusion_Detection_System.git
```

Navigate into the project:

```bash
cd Network_Intrusion_Detection_System
```

Create virtual environment:

```bash
python -m venv venv
```

Activate environment:

Windows:

```bash
venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Run application:

```bash
python run.py
```

Application runs at:

```
http://127.0.0.1:5000/
```

---

## 🧠 Engineering Highlights

✅ Designed modular Flask application structure
✅ Integrated machine learning inference pipeline
✅ Implemented automated data preprocessing workflow
✅ Applied object-oriented and reusable coding practices
✅ Used Git-based version control workflow
✅ Built an end-to-end ML application from data to deployment

---

## 📈 Future Improvements

* Containerization using Docker
* REST API improvements
* Cloud deployment
* Real-time alert notifications
* Deep learning based intrusion detection
* CI/CD pipeline integration

---

## 👨‍💻 Developer

**GOWNI VENKAT CHARAN**

---

## ⭐ Support

If you find this project useful, consider giving it a star ⭐ on GitHub.
