# 🔐 AI-Powered Firewall System

This project implements a **real-time firewall system powered by machine learning**, capable of monitoring live network traffic, detecting malicious behavior, and blocking suspicious IP addresses automatically.

It was developed as part of a university project (Phase 1 & 2) to demonstrate the practical use of AI in cybersecurity.

---

## 📌 Project Overview

Traditional firewalls rely on rule-based filtering, which can be rigid and ineffective against zero-day or evolving threats. This project introduces a more intelligent approach by:

- **Training a machine learning model** on network traffic data (CIC-IDS2017)
- **Monitoring live traffic** using `tshark`
- **Classifying packets in real time**
- **Blocking malicious IPs instantly** using `iptables`
- **Logging all detection events for analysis**

---

## 🚀 Features

- ✅ Real-time traffic capture via `tshark`
- ✅ Feature extraction & preprocessing
- ✅ Scikit-learn model integration (Random Forest or LightGBM)
- ✅ Automated IP blocking using `iptables`
- ✅ Logging blocked activity in `blocked_ips.log`
- ✅ Results analyzer script for reporting
- 🔒 Easily extendable to use neural networks or anomaly detection

---

## 🛠️ Installation & Setup

### 1. Clone the Repo

git clone https://github.com/AliHaram/AIPoweredFirewall.git
cd AIPoweredFirewall

### 2. Create Virtual Environment

python3 -m venv venv
source venv/bin/activate

### 3. Install Dependencies

pip install -r requirements.txt
# Or install manually
pip install pandas numpy scikit-learn joblib lightgbm
sudo apt install tshark iptables

### 4. Train the Model

Use the training script to train and save your model:

python train_firewall_model.py

This will generate:
- firewall_model.pkl
- scaler.pkl

---

## 🌐 Run the Firewall

To monitor live traffic and auto-block malicious IPs:

sudo ./venv/bin/python firewall_monitor.py

> The script runs continuously, inspecting one packet every second and blocking threats on the spot.

---

## 📊 Analyze Results

After running the firewall, use this to summarize all blocked activity:

python results_analysis.py

You'll get:
- Total blocked IPs
- Unique attackers
- Daily trends
- Repeat offenders

---

## 📁 Project Structure

```
firewall_project/
├── train_firewall_model.py     # Trains the model on labeled dataset
├── firewall_monitor.py         # Live monitoring + classification + blocking
├── results_analysis.py         # Summarizes logs for Phase 2 results
├── blocked_ips.log             # Stores all blocked IPs
├── firewall_model.pkl          # Saved trained ML model
├── scaler.pkl                  # Standard scaler used for input normalization
├── .gitignore
└── README.md
```

---

## 🧠 Technologies Used

- **Python 3.12**
- **Scikit-learn** for model training
- **Tshark** for live packet capture
- **Pandas & NumPy** for data manipulation
- **Joblib** for model saving
- **iptables** for packet blocking
- **GitHub** for version control and project hosting

---

## 📚 Future Enhancements

- 🔄 Use a sliding window for behavioral detection
- 🧠 Integrate deep learning (LSTM, Autoencoders)
- 🌍 Blocklists, geo-IP awareness, threat intelligence feeds
- 📊 Dashboard with real-time alerts (Flask or Streamlit)
- ✉️ Email or Discord notifications for critical attacks

---

## 📢 Author

**Ali Haram**
Project: *AI-Powered Firewall for Real-Time Threat Detection*
Repo: https://github.com/AliHaram/AIPoweredFirewall

---

## 📄 License

This project is open-source for educational purposes. You may adapt or extend it with proper citation :) 

