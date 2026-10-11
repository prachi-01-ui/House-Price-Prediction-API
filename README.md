# 🏡 House Price Prediction API

A Machine Learning-powered RESTful API built with **FastAPI**, **Scikit-learn**, **Pandas**, and **Uvicorn** for predicting California house prices[cite: 2]. Supports real-time single-sample inference and batch prediction via CSV uploads[cite: 2].

---

## 📌 Project Overview

This project provides an end-to-end Machine Learning pipeline and web service:
- **Exploratory Data Analysis (`explore.py`)**: Script for dataset inspection and feature engineering exploration[cite: 1].
- **Model Training (`train.py`)**: Trains the Random Forest Regressor on house feature data and exports local `.joblib` model/scaler artifacts[cite: 1, 2].
- **REST API Service (`main.py`)**: High-performance FastAPI server serving prediction endpoints[cite: 1, 2].

---

## 📁 Repository Structure

House-Price-Prediction-API/
├── explore.py              # Exploratory Data Analysis script
├── train.py                # Model training pipeline (generates .joblib artifacts)
├── main.py                 # FastAPI application & route handlers
├── requirements.txt        # Project dependencies
└── README.md               # Project documentation

---

## 🛠️ Tech Stack

* **Language:** Python 3.x[cite: 2]
* **Framework:** FastAPI, Uvicorn[cite: 1, 2]
* **Machine Learning:** Scikit-learn, Joblib[cite: 1, 2]
* **Data Processing:** Pandas, NumPy[cite: 1, 2]

---

## 🚀 Getting Started

### 1. Prerequisites
Ensure Python 3.8+ is installed on your machine.

### 2. Clone the Repository
git clone [https://github.com/prachi-01-ui/House-Price-Prediction-API.git](https://github.com/prachi-01-ui/House-Price-Prediction-API.git)
cd House-Price-Prediction-API

### 3. Set Up Virtual Environment & Install Dependencies
# Create virtual environment
python -m venv venv

# Activate virtual environment
# Windows:
venv\Scripts\activate
# macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt

---

## ⚙️ Running the Application

### 1. Generate Model Artifacts
Since model binaries are excluded from version control, run the training script first to generate `house_model.joblib` and `house_features.joblib`[cite: 1, 2]:
python train.py

### 2. Launch the FastAPI Server
uvicorn main:app --reload

The API server will start locally at `[http://127.0.0.1:8000](http://127.0.0.1:8000)`.

---

## 📖 API Documentation & Testing

FastAPI automatically generates interactive API documentation. Once the server is running, visit:

- **Swagger UI:** `[http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)`
- **ReDoc:** `[http://127.0.0.1:8000/redoc](http://127.0.0.1:8000/redoc)`

---

## ⚡ API Endpoints Summary

| Method | Endpoint | Description |
| :--- | :--- | :--- |
| `GET` | `/` | Health check endpoint |
| `POST` | `/predict` | Predict house price for a single feature record[cite: 2] |
| `POST` | `/predict-csv` | Upload CSV for bulk house price prediction & download results[cite: 2] |

---

## 📝 License

Distributed under the MIT License.
