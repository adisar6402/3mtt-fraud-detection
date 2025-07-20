# 🛡️ 3MTT Fraud Detection AI/ML Project

This mini-project simulates a real-world fraud detection system using a trained logistic regression model. The system is deployed via a FastAPI REST API, containerized using Docker, and demonstrates simulated real-time data streaming to emulate message queue behavior (like Kafka).

---

## 📌 Project Overview

- ✅ **Model**: Logistic Regression for binary classification (Fraudulent or Legit)  
- ⚙️ **API**: FastAPI-based prediction endpoint  
- 📦 **Containerization**: Docker-ready with simple build/run  
- 🔄 **Streaming**: Simulated real-time streaming using Python queue  
- 📁 **Platform**: Built and tested in Google Colab  

---

## 🧠 Model Training

The model was trained on a synthetic dataset of transactions with features:

- `age`
- `salary`
- `transaction_amount`

It was scaled using `StandardScaler`, trained using `LogisticRegression`, and both artifacts (`fraud_model.pkl` and `scaler.pkl`) were saved for deployment.

---

## 🚀 FastAPI Endpoint

The API receives POST requests with transaction data and responds with a fraud prediction.

### 🧪 Sample Input
```json
{
  "age": 45,
  "salary": 50000,
  "transaction_amount": 3000
}
```

### ✅ Sample Response
```json
{
  "prediction": "Fraudulent"
}
```

---

## 🐳 Docker Containerization

To make the FastAPI app portable and deployment-ready, we containerized it using Docker.

### 📄 Dockerfile
```Dockerfile
FROM python:3.9-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY fraud_api.py .
COPY fraud_model.pkl .
COPY scaler.pkl .

EXPOSE 8000

CMD ["uvicorn", "fraud_api:app", "--host", "0.0.0.0", "--port", "8000"]
```

### 📁 Project Structure
```
project/
│
├── fraud_api.py               # FastAPI prediction API  
├── fraud_model.pkl            # Trained logistic regression model  
├── scaler.pkl                 # Feature scaler  
├── requirements.txt           # App dependencies  
└── Dockerfile                 # Docker build instructions  
```

---

## 🔄 Real-Time Streaming Simulation

We simulated Kafka-like streaming using a Python loop and queue.

```python
import time, pandas as pd, joblib

model = joblib.load("fraud_model.pkl")
scaler = joblib.load("scaler.pkl")

transaction_stream = [
    {"age": 25, "salary": 30000, "transaction_amount": 800},
    {"age": 45, "salary": 50000, "transaction_amount": 3000},
    {"age": 38, "salary": 45000, "transaction_amount": 1500},
    {"age": 52, "salary": 70000, "transaction_amount": 5200},
]

print("🚀 Simulating real-time transaction stream...\n")
for txn in transaction_stream:
    input_df = pd.DataFrame([txn])
    input_scaled = scaler.transform(input_df)
    prediction = model.predict(input_scaled)[0]
    result = "Fraudulent" if prediction == 1 else "Legit"
    print(f"➡️ {txn} → 🧠 Prediction: {result}")
    time.sleep(0.5)

print("\n✅ Streaming simulation complete.")
```

---

## ⚡ Running with Ngrok (Google Colab)

To expose the FastAPI app in Google Colab:
```python
!pip install fastapi uvicorn nest-asyncio pyngrok -q

import nest_asyncio
from pyngrok import ngrok
import uvicorn

nest_asyncio.apply()
ngrok.set_auth_token("your_ngrok_token_here")
public_url = ngrok.connect(8000)
print(f"🔗 Public FastAPI URL: {public_url}")

uvicorn.run("fraud_api:app", host="0.0.0.0", port=8000)
```

---

## 🛠️ How to Run Locally with Docker

1. 🔧 Build the image:
```bash
docker build -t fraud-api .
```

2. 🚀 Run the container:
```bash
docker run -p 8000:8000 fraud-api
```

3. 🌐 Access the API:
```
http://localhost:8000/docs
```

---

## 📬 Author

**Abdulrahman Adisa Amuda**  
IBM Certified | AI/ML Enthusiast | 3MTT Trainee  
🔗 [GitHub Profile](https://github.com/adisar6402)

---

## ✅ Status

🎓 Project Complete & Ready for Evaluation  
📦 Fully Dockerized  
🧠 Machine Learning Integrated  
⚙️ FastAPI Operational  
🔄 Streaming Logic Simulated  

---

## 📢 License

This project is licensed for educational purposes under the MIT License.
