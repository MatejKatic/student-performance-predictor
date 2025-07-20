# Student Performance Predictor 🎓

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Demo](#-demo)
- [Tech Stack](#-tech-stack)
- [Installation](#-installation)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [Model Performance](#-model-performance)
- [API Reference](#-api-reference)

## 🌟 Overview

The Student Performance Predictor is a comprehensive machine learning solution that helps educational institutions and researchers predict student math scores based on various socio-economic and academic factors. The system uses advanced ML algorithms to provide accurate predictions, helping identify students who might need additional support.

### 🎯 Key Objectives

- Predict student math scores with high accuracy
- Identify key factors affecting student performance
- Provide an easy-to-use web interface for predictions
- Demonstrate ML best practices and pipeline implementation

## ✨ Features

- 🤖 **Multiple ML Models**: Implements and compares 7 different algorithms
- 📊 **Comprehensive Pipeline**: Complete ML pipeline from data ingestion to prediction
- 🌐 **Web Interface**: User-friendly Flask web application
- 📈 **Model Evaluation**: Automated model selection based on R² score
- 🔧 **Modular Architecture**: Clean, maintainable code structure
- 📝 **Logging System**: Comprehensive logging for debugging and monitoring
- ⚡ **Real-time Predictions**: Instant predictions through web interface

## 🖥️ Demo

### Input Features

The model takes the following inputs:

- **Gender**: Male/Female
- **Race/Ethnicity**: Group A-E
- **Parental Education Level**: Bachelor's degree, Master's degree, etc.
- **Lunch Type**: Standard/Free or Reduced
- **Test Preparation Course**: Completed/None
- **Reading Score**: 0-100
- **Writing Score**: 0-100

### Sample Prediction

**Input:**
```
Gender: Female
Race/Ethnicity: Group C
Parental Education: Bachelor's degree
Lunch: Standard
Test Preparation: Completed
Reading Score: 85
Writing Score: 82
```

**Predicted Math Score: 88.5**

## 🛠️ Tech Stack

### Backend

- **Python 3.8+**
- **Flask** - Web framework
- **NumPy** - Numerical computing
- **Pandas** - Data manipulation
- **Scikit-learn** - ML algorithms
- **XGBoost** - Gradient boosting
- **CatBoost** - Categorical boosting

### Frontend

- HTML5
- CSS3
- Bootstrap (optional)

### ML Models Implemented

1. Linear Regression
2. Random Forest Regressor
3. Decision Tree Regressor
4. Gradient Boosting Regressor
5. XGBoost Regressor
6. CatBoost Regressor
7. AdaBoost Regressor

## 🚀 Installation

### Prerequisites

- Python 3.8 or higher
- pip package manager
- Git

### Step-by-Step Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/student-performance-predictor.git
   cd student-performance-predictor
   ```

2. **Create a virtual environment**
   ```bash
   python -m venv venv
   ```
   
   **On Windows:**
   ```bash
   venv\Scripts\activate
   ```
   
   **On macOS/Linux:**
   ```bash
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set up the project**
   ```bash
   python setup.py install
   ```

## 📖 Usage

### Running the Application

1. **Start the Flask server**
   ```bash
   python app.py
   ```

2. **Access the application**
   - Open your browser and navigate to `http://localhost:5000`
   - You'll see the home page with the prediction form

3. **Make predictions**
   - Fill in all the required fields
   - Click "Predict" to get the math score prediction

### Training the Model

To retrain the model with new data:

```bash
python src/components/data_ingestion.py
```

This will:
- Load the data
- Split into train/test sets
- Apply transformations
- Train multiple models
- Select the best model
- Save the model and preprocessor

## 📁 Project Structure

```
student-performance-predictor/
│
├── artifacts/                 # Trained models and preprocessors
│   ├── model.pkl
│   ├── preprocessor.pkl
│   └── data files
│
├── notebook/                  # Jupyter notebooks for EDA
│   └── data/
│       └── stud.csv          # Original dataset
│
├── src/
│   ├── components/
│   │   ├── __init__.py
│   │   ├── data_ingestion.py
│   │   ├── data_transformation.py
│   │   └── model_trainer.py
│   │
│   ├── pipeline/
│   │   ├── __init__.py
│   │   ├── predict_pipeline.py
│   │   └── train_pipeline.py
│   │
│   ├── __init__.py
│   ├── exception.py          # Custom exception handling
│   ├── logger.py             # Logging configuration
│   └── utils.py              # Utility functions
│
├── templates/                 # HTML templates
│   ├── index.html
│   └── home.html
│
├── app.py                     # Flask application
├── requirements.txt           # Project dependencies
├── setup.py                   # Project setup file
└── README.md                  # Project documentation
```

## 📊 Model Performance

### Model Comparison

| Model | R² Score | Training Time |
|-------|----------|---------------|
| CatBoost Regressor | 0.88 | 2.3s |
| XGBoost Regressor | 0.87 | 1.8s |
| Random Forest | 0.86 | 1.2s |
| Gradient Boosting | 0.85 | 2.1s |
| Decision Tree | 0.72 | 0.3s |
| Linear Regression | 0.69 | 0.1s |
| AdaBoost | 0.68 | 1.5s |

> **Note:** The best model is automatically selected based on R² score

## 🔌 API Reference

### Prediction Endpoint

```http
POST /predictdata
```

#### Request Body

```json
{
  "gender": "male",
  "race_ethnicity": "group B",
  "parental_level_of_education": "bachelor's degree",
  "lunch": "standard",
  "test_preparation_course": "none",
  "reading_score": 72,
  "writing_score": 74
}
```

#### Response

```json
{
  "prediction": 76.5
}
```
