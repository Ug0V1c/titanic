# Titanic Survival Prediction System

A machine learning web application that predicts whether a passenger would have survived the Titanic disaster based on their characteristics.

## 🎯 Project Overview

This project implements a Random Forest Classifier to predict Titanic passenger survival using five key features:
- **Pclass**: Passenger Class (1st, 2nd, 3rd)
- **Sex**: Gender (Male/Female)
- **Age**: Age in years
- **Fare**: Ticket price
- **Embarked**: Port of Embarkation (C=Cherbourg, Q=Queenstown, S=Southampton)

## 🏗️ Project Structure

```
Titanic_Project_YourName_MatricNo/
├── app.py                          # Flask web application
├── requirements.txt                # Python dependencies
├── render.yaml                     # Render deployment config
├── README.md                       # Project documentation
├── model/
│   ├── model_building.ipynb        # Model training notebook
│   └── titanic_survival_model.pkl  # Trained model file
└── templates/
    └── index.html                  # Web interface
```

## 🚀 Features

- **Machine Learning Model**: Random Forest Classifier with 85%+ accuracy
- **Web Interface**: User-friendly Flask web application
- **Real-time Predictions**: Instant survival predictions with probability scores
- **Responsive Design**: Works on desktop and mobile devices
- **Model Persistence**: Pre-trained model saved using Joblib

## 📊 Model Performance

- **Algorithm**: Random Forest Classifier
- **Features Used**: 5 selected features
- **Accuracy**: ~85% on test set
- **Preprocessing**: Missing value imputation, feature encoding, standardization

## 🛠️ Local Installation

### Prerequisites
- Python 3.8 or higher
- pip package manager

### Setup Steps

1. Clone the repository:
```bash
git clone https://github.com/yourusername/Titanic_Project_YourName_MatricNo.git
cd Titanic_Project_YourName_MatricNo
```

2. Create a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Run the application:
```bash
python app.py
```

5. Open your browser and navigate to:
```
http://localhost:5000
```

## ☁️ Deployment on Render.com

### Step 1: Prepare Your Repository

1. Ensure all files are in your GitHub repository
2. Make sure `titanic_survival_model.pkl` is in the `model/` folder
3. Verify `render.yaml` is in the root directory

### Step 2: Deploy on Render

1. Go to [Render.com](https://render.com) and sign in
2. Click "New +" and select "Web Service"
3. Connect your GitHub repository
4. Render will automatically detect the `render.yaml` configuration
5. Click "Create Web Service"
6. Wait for deployment to complete (5-10 minutes)

### Step 3: Access Your Application

Once deployed, Render will provide a URL like:
```
https://titanic-survival-prediction.onrender.com
```

## 📝 Usage

1. Open the web application
2. Enter passenger details:
   - Select passenger class (1st, 2nd, or 3rd)
   - Choose gender (Male or Female)
   - Enter age (0-100 years)
   - Enter fare amount (ticket price in dollars)
   - Select embarkation port
3. Click "Predict Survival"
4. View the prediction result with probability score

## 🧪 Model Training

The model was trained using Google Colab. To retrain:

1. Open `model/model_building.ipynb` in Google Colab
2. Run all cells sequentially
3. Download the generated `titanic_survival_model.pkl`
4. Replace the file in the `model/` folder

## 📋 Model Details

### Selected Features
- **Pclass**: Strong predictor (1st class had higher survival)
- **Sex**: Critical feature (females had much higher survival)
- **Age**: Important (children had priority)
- **Fare**: Correlates with passenger class
- **Embarked**: Moderate influence on survival

### Preprocessing Steps
1. Missing value imputation (median for numerical, mode for categorical)
2. Label encoding for categorical variables
3. Feature standardization using StandardScaler
4. Train-test split (80-20 ratio)

### Model Configuration
```python
RandomForestClassifier(
    n_estimators=100,
    max_depth=10,
    min_samples_split=5,
    min_samples_leaf=2,
    random_state=42
)
```

## 🔍 API Endpoints

### GET /
Returns the main web interface

### POST /predict
Accepts form data and returns prediction

**Request Body (form-data)**:
```
pclass: 1-3
sex: male/female
age: 0-100
fare: 0-1000
embarked: C/Q/S
```

**Response**:
```json
{
    "prediction": 1,
    "result": "Survived",
    "probability": 0.85,
    "confidence": 0.85,
    "passenger_info": {...}
}
```

### GET /health
Health check endpoint for monitoring

## 🤝 Contributing

This is an academic project. For improvements:
1. Fork the repository
2. Create a feature branch
3. Submit a pull request

## 📄 License

This project is created for educational purposes.

## 👨‍💻 Author

**Your Name**  
Matric No: Your Matric Number  
Course: Machine Learning / Data Science  

## 🙏 Acknowledgments

- Dataset: [Kaggle Titanic Dataset](https://www.kaggle.com/c/titanic)
- Framework: Flask
- ML Library: scikit-learn
- Deployment: Render.com

## 📞 Support

For issues or questions:
- Create an issue on GitHub
- Contact: your.email@example.com

---

**Note**: This project was developed as part of an academic assignment demonstrating machine learning model development and deployment.