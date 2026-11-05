<div align="center">

# 🛡️ Network Intrusion Detection System

**Machine learning-based detection of malicious network traffic, powered by a Random Forest classifier and served through a Flask web dashboard.**

![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Model](https://img.shields.io/badge/Model-Random%20Forest-2ea44f?style=for-the-badge)

[Repository](https://github.com/Chintucharan/Network_Intrusion_Detection_System) ·
[Report a Bug](https://github.com/Chintucharan/Network_Intrusion_Detection_System/issues) ·
[Request a Feature](https://github.com/Chintucharan/Network_Intrusion_Detection_System/issues)

</div>

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [System Workflow](#system-workflow)
- [Why Random Forest](#why-random-forest)
- [Screenshots](#screenshots)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Roadmap](#roadmap)
- [Disclaimer](#disclaimer)
- [Author](#author)

---

## Overview

Traditional rule-based monitoring struggles to keep pace with new and evolving cyber threats. This project applies machine learning to network traffic features and classifies each record as **normal** or **malicious**.

It demonstrates the complete lifecycle of an ML application: traffic analysis, data preprocessing, model training and persistence, real-time inference, and a web interface for exploring results.

## Features

| | Feature | Description |
| :-: | --- | --- |
| 📡 | **Traffic analysis** | Captures and inspects packets using Scapy and PyShark |
| 🧩 | **Feature extraction** | Converts raw traffic into model-ready features |
| 🌲 | **ML-based detection** | A trained Random Forest classifier labels every record |
| 💾 | **Model persistence** | The model is saved with Joblib and loaded at runtime, so no retraining is needed |
| 🖥️ | **Web dashboard** | A Flask interface displaying detection results and predictions |
| 📊 | **Visualization** | Matplotlib and Seaborn charts for traffic patterns and model behavior |

## System Workflow

### 1. End-to-end detection pipeline

```mermaid
flowchart LR
    A["Network<br/>Traffic"] --> B["Packet Capture<br/>Scapy / PyShark"]
    B --> C["Feature<br/>Extraction"]
    C --> D["Preprocessing<br/>Pandas / NumPy"]
    D --> E["Random Forest<br/>Classifier"]
    E --> F{"Prediction"}
    F -->|Normal| G["Normal Traffic"]
    F -->|Attack| H["Malicious Traffic"]
    G --> I["Flask Dashboard"]
    H --> I

    classDef input fill:#e8f1fb,stroke:#3776ab,color:#0b2a4a
    classDef process fill:#fff4e0,stroke:#f7931e,color:#4a2c00
    classDef model fill:#e6f6ec,stroke:#2ea44f,color:#0b3a1c
    classDef good fill:#e6f6ec,stroke:#2ea44f,color:#0b3a1c
    classDef bad fill:#fdeaea,stroke:#d73a49,color:#5a0b14
    classDef output fill:#efe9fb,stroke:#6f42c1,color:#2a1457

    class A,B input
    class C,D process
    class E,F model
    class G good
    class H bad
    class I output
```

### 2. Model lifecycle: train once, predict many times

```mermaid
flowchart LR
    subgraph TRAIN["Offline: Training"]
        direction LR
        T1["Dataset"] --> T2["Preprocessing"] --> T3["Train<br/>Random Forest"] --> T4["Evaluate"] --> T5[("Save model<br/>Joblib")]
    end

    subgraph SERVE["Online: Inference"]
        direction LR
        S1[("Load model<br/>Joblib")] --> S2["Preprocess<br/>incoming data"] --> S3["Predict"] --> S4["Show result<br/>on dashboard"]
    end

    T5 -. "models/" .-> S1
```

### 3. Request flow

```mermaid
sequenceDiagram
    autonumber
    actor User
    participant UI as Web Dashboard
    participant API as Flask Routes
    participant PRE as Preprocessing Module
    participant ML as Random Forest Model

    User->>UI: Submit traffic features
    UI->>API: HTTP request
    API->>PRE: Validate and preprocess
    PRE->>ML: Feature vector
    ML-->>API: Label (Normal / Attack)
    API-->>UI: Prediction result
    UI-->>User: Display result and charts
```

## Why Random Forest

- ✅ Performs well on **tabular, mixed-type network data**.
- ✅ Combines many decision trees, making it **less prone to overfitting** than a single tree.
- ✅ Exposes **feature importance**, showing which traffic attributes drive detection.
- ✅ Delivers **fast predictions**, which suits monitoring use cases.

## Screenshots

<table>
  <tr>
    <td align="center" width="50%">
      <b>Network Monitoring Dashboard</b><br/><br/>
      <img src="screenshots/page.png" alt="Network Intrusion Detection Dashboard" width="100%"/>
    </td>
    <td align="center" width="50%">
      <b>Prediction Results</b><br/><br/>
      <img src="screenshots/prediction.png" alt="Prediction Result" width="100%"/>
    </td>
  </tr>
  <tr>
    <td align="center" width="50%">
      <b>Traffic Analysis</b><br/><br/>
      <img src="screenshots/charts-1.png" alt="Traffic Analysis Chart" width="100%"/>
    </td>
    <td align="center" width="50%">
      <b>Model Performance</b><br/><br/>
      <img src="screenshots/charts-2.png" alt="Model Performance Chart" width="100%"/>
    </td>
  </tr>
</table>

## Tech Stack

| Category | Tools |
| --- | --- |
| **Language** | Python |
| **Backend** | Flask |
| **Machine Learning** | Scikit-learn (Random Forest), Joblib |
| **Network Analysis** | Scapy, PyShark |
| **Data Processing** | Pandas, NumPy |
| **Visualization** | Matplotlib, Seaborn |
| **Tooling** | Git, virtual environments |

## Project Structure

```text
Network_Intrusion_Detection_System/
├── app/
│   ├── routes.py          # Flask routes
│   └── modules/           # Preprocessing and prediction logic
├── models/                # Trained ML model
├── dataset/               # Dataset files
├── screenshots/           # README images
├── static/                # CSS, JS, assets
├── templates/             # HTML templates
├── run.py                 # Application entry point
├── requirements.txt
├── .gitignore
└── README.md
```

## Getting Started

### Prerequisites

- Python **3.9** or later
- For live packet capture: administrator/root access, plus **Npcap** (Windows) or **libpcap** (Linux/macOS)

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/Chintucharan/Network_Intrusion_Detection_System.git
cd Network_Intrusion_Detection_System

# 2. Create and activate a virtual environment
python -m venv venv
venv\Scripts\activate          # Windows
source venv/bin/activate       # Linux / macOS

# 3. Install dependencies
pip install -r requirements.txt

# 4. Run the application
python run.py
```

Then open **http://127.0.0.1:5000/** in your browser.

## Roadmap

- [ ] Docker containerization
- [ ] REST API for predictions
- [ ] Real-time security alerts
- [ ] Comparison with other models (XGBoost, SVM, deep learning)
- [ ] Unit tests and CI/CD with GitHub Actions
- [ ] Cloud deployment

Have an idea? [Open an issue](https://github.com/Chintucharan/Network_Intrusion_Detection_System/issues).

## Disclaimer

This project is for **educational and research purposes only**. Use it only on networks you own or have explicit permission to monitor.

## Author

**Gowni Venkat Charan**

[![GitHub](https://img.shields.io/badge/GitHub-Chintucharan-181717?style=flat&logo=github)](https://github.com/Chintucharan)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat&logo=linkedin)](https://www.linkedin.com/in/gowni-venkat-charan-1b06562a8/)

**More projects:** 🎮 [Color Mania](https://github.com/Chintucharan/simongame), a memory sequence game ([Live Demo](https://chintucharan.github.io/simongame/))

---

<div align="center">

If you found this project useful, consider giving it a ⭐

</div>
