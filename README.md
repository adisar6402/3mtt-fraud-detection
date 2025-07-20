# 🚀 3MTT AI/ML Final Project — Fraud Detection API with Streaming (Colab Simulation)

> ✅ Author: **Abdulrahman Adisa Amuda**  
> 🏁 Program: **3MTT Nigeria — AI/ML Track**  
> 🗓️ Module 7 Mini Project  
> 📄 Submission: `Abdulrahman_Adisa_Amuda__module_7_mini_project.ipynb`

---

## 📌 Project Description

This project simulates deploying a **fraud detection machine learning model** as a **REST API** using FastAPI and simulates **real-time predictions using Kafka-style streaming** — all within **Google Colab**, in compliance with storage and environment limitations.

The system predicts whether a transaction is **fraudulent** or **legit** based on sample financial data. It includes:

- Logistic Regression classifier  
- Input validation  
- Joblib-based model persistence  
- A simulation of real-time streaming via Python loop  
- Full step-by-step workflow aligned with the project requirements  

---

## 📂 Project Structure

```
3mtt-fraud-api/
├── Abdulrahman_Adisa_Amuda__module_7_mini_project.ipynb
├── fraud_model.pkl
├── scaler.pkl
└── README.md
```

---

## ✅ Completed Tasks

### 🧠 Model Development
- [x] Generated a sample dataset mimicking credit card transactions  
- [x] Preprocessed and scaled the features  
- [x] Trained a Logistic Regression model  
- [x] Saved the model and scaler with `joblib`  

### 🔧 API Simulation
- [x] Defined a `predict_transaction()` function simulating a FastAPI endpoint  
- [x] Tested the function with a sample transaction  

### 📡 Real-Time Streaming Simulation
- [x] Created a loop to simulate Kafka-style transaction streaming  
- [x] Performed live prediction on each transaction  
- [x] Delayed each prediction with `time.sleep()` to mimic streaming  

---

## 📊 Sample Output

```text
✅ Model and Scaler saved.
🧪 Test Prediction: Fraudulent

🚦 Real-time transaction stream:
➡️ {'age': 45, 'salary': 50000, 'transaction_amount': 3000} → 🧠 Prediction: Fraudulent
➡️ {'age': 28, 'salary': 25000, 'transaction_amount': 1200} → 🧠 Prediction: Legit
➡️ {'age': 52, 'salary': 70000, 'transaction_amount': 5000} → 🧠 Prediction: Fraudulent

✅ Streaming simulation complete.
```

---

## 🛠️ Tools & Technologies Used

| Tool        | Purpose                             |
|-------------|-------------------------------------|
| Python      | Core programming language           |
| Scikit-learn| Model training (Logistic Regression)|
| Pandas      | Data manipulation                   |
| Joblib      | Saving model and scaler             |
| Google Colab| Notebook simulation environment     |

---

## 🧾 How to Run the Notebook

1. Open [Google Colab](https://colab.research.google.com)  
2. Upload the notebook file: `Abdulrahman_Adisa_Amuda__module_7_mini_project.ipynb`  
3. Run cells sequentially  
4. View outputs inline  

---

## 🏁 Status

✅ **100% Complete**  
📤 **Ready for grading and submission**

---

## ✨ Bonus (Optional)

- [ ] Integrate actual Kafka with ngrok tunnels  
- [ ] Deploy FastAPI to Render/Heroku  
- [ ] Add authentication to prediction endpoint  

---

> © Abdulrahman Adisa Amuda – 3MTT Final Project — AI/ML Track  
> _Proudly simulated on Colab due to system storage limitations 🚀_
