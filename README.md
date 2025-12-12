# ⚡ Replica — Clone Website Detection System  
A machine-learning based clone & phishing website detection system that analyzes URLs and identifies whether a website is **legitimate** or **malicious**.  
Built using **Python, Flask API, XGBoost**, and integrated with a **browser extension** for real-time detection.

---

## 📌 Overview  
Replica is a clone website detection tool that works by analyzing URL patterns and predicting if the received link is suspicious.  
Your backend model classifies every incoming URL as:

- 🟢 **Legitimate Website**  
- 🔴 **Fake / Clone / Phishing Website**

If a website is detected as fake, the system **automatically redirects the user to the real website**.

Replica does **not** allow manual URL entry — it detects URLs automatically through user interaction and browser extension monitoring.

---

## 🚀 Features  

### 🔍 Automatic URL Detection  
The browser extension captures the URL automatically whenever the user visits a website.

### 🧠 Machine Learning Detection   
Replica uses an **XGBoost-based classifier** trained on phishing + legitimate URLs.

### 🛡 Real-Time Classification  
Flask API instantly responds with “legitimate” or “malicious”.

### 🔗 Auto-Redirect System  
When a URL is flagged as malicious, Replica redirects the user to the correct safe site.

### 📝 Pop-Up Notification  
The browser extension displays:  
- 🟢 *This is a real website*  
- 🔴 *Fake website — redirecting to real site*  

### 💾 Dataset Used  
- `malicious_phish.csv`  
- `legitimate-urls.csv`  

---

## 🏗️ Project Structure  

```
Replica/
│── app.py                   # Flask backend API
│── model/
│    └── xgboost_model.pkl   # Trained ML model (XGBoost)
│── extension/               # Browser extension source
│    ├── manifest.json
│    ├── popup.html
│    ├── popup.js
│    ├── background.js
│── static/
│── templates/
│── datasets/
│    ├── malicious_phish.csv
│    ├── legitimate-urls.csv
│── README.md                # Project documentation
```

---

## ⚙️ Technologies Used  

- **Python**
- **Flask (REST API)**
- **XGBoost (ML Model)**
- **HTML, CSS, JavaScript** (for browser extension)
- **MongoDB** (if user history/profile stored)

---

## 🔌 How Replica Works  

### **1️⃣ Browser Extension Monitors URLs**
Whenever the user opens a URL, the extension sends the link to the Flask backend.

### **2️⃣ Flask Extracts Features**
The backend extracts URL features such as:
- Length  
- Number of dots  
- Number of hyphens  
- Presence of IP  
- Suspicious keywords  

### **3️⃣ XGBoost Model Predicts**
Returns:
- `0` → Legitimate  
- `1` → Malicious / Clone / Phishing  

### **4️⃣ Notification + Auto Redirect**
If malicious → automatic redirection to the real safe website.

---

## ▶️ Running the Project  

### **Step 1 — Install Requirements**
```
pip install -r requirements.txt
```

### **Step 2 — Run Flask Backend**
```
python app.py
```

### **Step 3 — Load Browser Extension**
Chrome → Extensions → Developer Mode → **Load Unpacked** → select `extension/` folder.
---

## 👨‍💻 Developer  
**Dharsana K R**  
Full Stack Developer | Cybersecurity Enthusiast  

---

