# 🌸 Iris Flower Classification Using Machine Learning

## 📌 Project Overview

This project implements a Machine Learning classification system to identify Iris flower species based on their physical measurements.

It uses two classification algorithms, **Logistic Regression** and **K-Nearest Neighbors (KNN)**, to classify flowers into three species: Setosa, Versicolor, and Virginica.

The project also includes data visualization, feature standardization, model evaluation, model serialization using Pickle, and a Flask REST API for making predictions through HTTP requests.

## 🎯 Project Objectives

- Explore the Iris dataset and understand its feature distributions.
- Analyze relationships between flower measurements and species.
- Visualize class distribution and feature relationships.
- Standardize numerical features using StandardScaler.
- Train Logistic Regression and KNN classification models.
- Evaluate model performance using classification metrics.
- Save the trained model and scaler for reuse.
- Deploy the trained model through a Flask prediction API.

## 📂 Dataset

**Dataset:** Iris Flower Dataset (Scikit-learn built-in dataset).

The dataset contains 150 samples, four numerical features, and three flower species.

### Input Features

| Feature | Description |
|---|---|
| Sepal Length | Length of the flower sepal |
| Sepal Width | Width of the flower sepal |
| Petal Length | Length of the flower petal |
| Petal Width | Width of the flower petal |

### Target Classes

The model predicts one of three Iris species:

- `0` – Setosa
- `1` – Versicolor
- `2` – Virginica

## 🛠️ Technologies and Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Flask
- Pickle

## 🔍 Exploratory Data Analysis (EDA)

The project performs visual analysis to understand the dataset.

### Visualizations Included

1. **Class Distribution:** Count plot showing the number of samples in each species.
2. **Pairplot:** KDE-based pairplot to explore feature distributions and relationships across species.
3. **Logistic Regression Confusion Matrix:** Visualizes classification performance.
4. **KNN Confusion Matrix:** Visualizes predictions from the KNN classifier.

## ⚙️ Data Preprocessing

### 1. Dataset Loading

The Iris dataset is loaded using Scikit-learn's `load_iris()` function and converted into a Pandas DataFrame for analysis.

### 2. Train-Test Split

The dataset is divided into:

- Training data: 80%
- Testing data: 20%
- Random state: 42

### 3. Feature Scaling

`StandardScaler` is used to standardize the numerical input features.

The scaler is fitted on training data and then applied to both training and testing data.

This ensures that the test data does not influence the scaling parameters.

## 🤖 Machine Learning Models

Two classification algorithms are implemented and evaluated.

### 1. Logistic Regression

Logistic Regression is used as a multiclass classification algorithm to predict Iris flower species.

**Configuration:**
- Algorithm: LogisticRegression
- Maximum iterations: 200

### 2. K-Nearest Neighbors (KNN)

KNN classifies a flower based on the species of its nearest neighboring samples in the feature space.

**Configuration:**
- Algorithm: KNeighborsClassifier
- Number of neighbors: 3

Both models are trained using standardized features.

## 📊 Model Evaluation

The models are evaluated using:

- **Accuracy:** Measures the proportion of correct predictions.
- **Precision:** Measures the correctness of positive class predictions.
- **Recall:** Measures how many actual samples of each class are correctly identified.
- **F1-Score:** Provides a balance between precision and recall.
- **Confusion Matrix:** Displays correct and incorrect classifications for each species.

The project generates classification reports and confusion matrix visualizations for both algorithms.

## 💾 Model Saving

The trained Logistic Regression model and StandardScaler are saved using Pickle.

```python
import pickle

with open("iris_model.pkl", "wb") as f:
    pickle.dump(model, f)

with open("Scaler.pkl", "wb") as f:
    pickle.dump(Scaler, f)
```

Saved files:

- `iris_model.pkl` – Trained Logistic Regression model.
- `Scaler.pkl` – Fitted StandardScaler.

## 🌐 Flask REST API Deployment

The project integrates Flask to expose the trained model through an HTTP API.

### Available Endpoints

| Endpoint | Method | Description |
|---|---|---|
| `/` | GET | Checks whether the Iris API is running |
| `/predict` | POST | Predicts the Iris flower species |

### Example Prediction Request

**POST:** `/predict`

Request JSON:

```json
{
    "data": [5.1, 3.5, 1.4, 0.2]
}
```

### Example Response

```json
{
    "prediction": "setosa"
}
```

The API receives flower measurements, scales the input, predicts the numerical class, and returns the corresponding species name.

## 🚀 Installation and Usage

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/iris-flower-classification.git
```

### 2. Navigate to the Project Directory

```bash
cd iris-flower-classification
```

### 3. Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn flask
```

### 4. Run the Application

First, run the training notebook or script to generate:

- `iris_model.pkl`
- `Scaler.pkl`

Then start the Flask application:

```bash
python app.py
```

### 5. Test the API

Send a POST request to:

```text
http://127.0.0.1:5000/predict
```

Use the JSON input shown in the Flask API section.

## 📁 Project Structure

```text
Iris-Flower-Classification/
│
├── iris_classification.ipynb
├── app.py
├── iris_model.pkl
├── Scaler.pkl
├── README.md
│
└── requirements.txt
```

## 🔧 Future Improvements

- Compare Logistic Regression and KNN using test accuracy and other metrics.
- Perform hyperparameter tuning for KNN.
- Add input validation and error handling to the Flask API.
- Build an interactive web interface for flower classification.
- Add probability scores using `predict_proba()`.
- Deploy the Flask application using Docker or a cloud platform.
- Add automated API testing.

## 👨‍💻 Author

**Muhammad Idrees**  
AI & Machine Learning Developer

Interested in Machine Learning, Deep Learning, Computer Vision, NLP, and AI-powered applications.

⭐ If you find this project useful, consider giving the repository a star!
