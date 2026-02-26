Here is your **README.md** in plain text format (English), ready to upload to GitHub:

---

# Indonesia Climate Weather Prediction (Binary Classification)

## 📌 Project Overview

This project builds a **Deep Learning Binary Classification Model** to predict **next-day weather conditions (Rain or Clear)** based on historical climate data from Indonesia.

The model is trained using meteorological features such as temperature, humidity, and wind speed. It uses a Neural Network built with TensorFlow / Keras.

The dataset is automatically downloaded from Kaggle using `kagglehub`.

---

## 📊 Dataset

Dataset source:
Indonesia Climate Dataset by greegtitan on Kaggle

Files used:

* `climate_data.csv`
* `province_detail.csv`
* `station_detail.csv`

The data includes weather station information, province information, and daily climate measurements.

---

## 🎯 Objective

To predict:

> **Will it rain tomorrow or not?**

Binary Classification Output:

* `Rain`
* `Clear`

Rain is determined based on rainfall (RR) value:

* If RR > 0.5 → Rain
* Else → Clear

---

## 🧠 Features Used

The model uses the following input features:

* `Tn` → Minimum Temperature
* `Tx` → Maximum Temperature
* `Tavg` → Average Temperature
* `RH_avg` → Average Humidity
* `ff_x` → Maximum Wind Speed
* `ff_avg` → Average Wind Speed

Target:

* `Target_Cuaca_Besok` (Next Day Weather)

---

## ⚙️ Data Processing Steps

1. Download dataset using kagglehub
2. Merge climate, station, and province data
3. Convert date format and sort by station
4. Generate today's weather label
5. Shift label to create next-day prediction target
6. Handle missing values using forward fill, backward fill, and median
7. Encode target labels using LabelEncoder
8. Normalize features using MinMaxScaler
9. Split dataset (70% train, 30% test without shuffling)

---

## 🏗 Model Architecture

Neural Network Architecture:

* Dense (64 units, ReLU)
* Dense (64 units, ReLU)
* Dense (1 unit, Sigmoid)

Configuration:

* Optimizer: Adam
* Loss Function: Binary Crossentropy
* Metric: Accuracy
* Epochs: 100

---

## 📈 Model Evaluation

The model is evaluated using test data after training.

Metric used:

* Accuracy

---

## 🌦 Example Predictions

The model supports custom weather prediction for any region by providing:

* Minimum Temperature
* Maximum Temperature
* Average Temperature
* Humidity
* Wind Speed

Example cities tested:

* Surabaya
* Jakarta

The prediction output includes:

* Weather classification
* Rain probability (%)

---

## 💾 Saved Artifacts

After training, the following files are generated:

* `model_cuaca_biner.keras` → Trained Neural Network model
* `scaler_cuaca.pkl` → MinMaxScaler object
* `encoder_cuaca.pkl` → LabelEncoder object

These files allow deployment without retraining.

---

## 🛠 Technologies Used

* Python
* NumPy
* Pandas
* TensorFlow / Keras
* Scikit-learn
* KaggleHub
* Joblib

---

## 🚀 How to Run

1. Install dependencies:

```
pip install numpy pandas tensorflow scikit-learn kagglehub joblib
```

2. Run the script:

```
python your_script_name.py
```

The dataset will be downloaded automatically.

---

## 📌 Future Improvements

* Add more meteorological features
* Use LSTM for time-series modeling
* Apply Time-Series Cross Validation
* Deploy using Streamlit or FastAPI
* Add visualization dashboard

---

## 👤 Author

Muhammad Auffa Hakim Aditya

