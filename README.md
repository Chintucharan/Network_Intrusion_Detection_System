# Network Intrusion Detection System

## Overview
The Network Intrusion Detection System (NIDS) is a machine learning-based application that detects malicious network traffic by analyzing network flow features. It provides real-time intrusion prediction through a Flask web application, helping identify potential cyber threats efficiently.

---

## Features
- Detects normal and malicious network traffic
- Machine Learning-based intrusion prediction
- Real-time prediction using a trained model
- User-friendly Flask web interface
- Feature preprocessing using scaling and label encoding
- Upload network traffic data for analysis

---

## Tech Stack
- Python
- Flask
- Scikit-learn
- Pandas
- NumPy
- Scapy
- Matplotlib

---

## Project Structure

```
NETWORK_INTRUSION_DETECTION/
│
├── app/
│   ├── static/
│   ├── templates/
│   ├── routes.py
│   └── __init__.py
│
├── dataset/
├── uploads/
├── train_model.py
├── run.py
├── network_intrusion_model.pkl
├── network_intrusion_scaler.pkl
├── network_intrusion_label_encoders.pkl
├── intrusion.pkl
├── requirements.txt
└── README.md
```

---

## Installation

1. Clone the repository

```bash
git clone https://github.com/yourusername/network-intrusion-detection.git
cd network-intrusion-detection
```

2. Create a virtual environment

```bash
python -m venv venv
```

3. Activate the virtual environment

**Windows**

```bash
venv\Scripts\activate
```

**Linux/macOS**

```bash
source venv/bin/activate
```

4. Install dependencies

```bash
pip install -r requirements.txt
```

5. Run the application

```bash
python run.py
```

Open your browser and visit:

```
http://127.0.0.1:5000
```

---

## Train the Model

To retrain the model:

```bash
python train_model.py
```

---

## Dependencies

- Flask
- Pandas
- NumPy
- Scikit-learn
- Scapy
- Matplotlib

Install all dependencies using:

```bash
pip install -r requirements.txt
```

---

## Future Enhancements

- Real-time packet capture
- Deep learning-based detection
- Interactive dashboard
- Cloud deployment
- REST API integration

---

## Author

GOWNI VENKAT CHARAN
---

## License

This project is licensed under the MIT License.