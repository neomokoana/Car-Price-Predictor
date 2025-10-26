# 🚗 Car Price Prediction System

A machine learning web application that predicts the selling price of used cars based on various specifications and features.

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Flask](https://img.shields.io/badge/Flask-2.0+-green.svg)
![scikit-learn](https://img.shields.io/badge/scikit--learn-1.0+-orange.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

## 📋 Table of Contents

- [About](#about)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Model Details](#model-details)
- [Screenshots](#screenshots)
- [Future Enhancements](#future-enhancements)
- [Contributing](#contributing)
- [License](#license)

## 📖 About

The Car Price Prediction System is a machine learning-powered web application that estimates used car selling prices. It helps both sellers price their vehicles competitively and buyers verify if listing prices are fair. The system uses a Random Forest Regressor trained on historical car sales data to provide accurate price predictions.

## ✨ Features

- 🎯 **Accurate Predictions**: Uses Random Forest Regressor with optimized hyperparameters
- 📊 **Multiple Input Parameters**: Year, price, kilometers, owners, fuel type, seller type, transmission
- 🌐 **User-Friendly Interface**: Clean, responsive web design
- ⚡ **Real-Time Results**: Instant price predictions
- 🔧 **Advanced Preprocessing**: Feature engineering and data transformation
- 📈 **Model Optimization**: Hyperparameter tuning using RandomizedSearchCV

## 🛠️ Technologies Used

### Backend

- **Python 3.8+**
- **Flask** - Web framework
- **scikit-learn** - Machine learning
- **Pandas** - Data manipulation
- **NumPy** - Numerical computations
- **Pickle** - Model serialization

### Frontend

- **HTML5**
- **CSS3**
- **Jinja2** - Template engine

### Data Science

- **Seaborn** - Data visualization
- **Matplotlib** - Plotting
- **RandomForestRegressor** - ML algorithm

## 📦 Installation

### Prerequisites

- Python 3.8 or higher
- pip (Python package manager)

### Step 1: Clone the Repository

```bash
git clone https://github.com/yourusername/car-price-prediction.git
cd car-price-prediction
```

### Step 2: Create Virtual Environment

```bash
# Windows
python -m venv venv
venv\Scripts\activate

# Mac/Linux
python3 -m venv venv
source venv/bin/activate
```

### Step 3: Install Dependencies

```bash
pip install -r requirements.txt
```

### Step 4: Run the Application

```bash
python app.py
```

The application will be available at `http://127.0.0.1:5000`

## 🚀 Usage

1. **Open the application** in your web browser at `http://127.0.0.1:5000`

2. **Enter car details:**

   - Year of Purchase (e.g., 2015)
   - Current Showroom Price in Lakhs (e.g., 5.59)
   - Kilometers Driven (e.g., 45000)
   - Number of Previous Owners (0-3)
   - Fuel Type (Petrol/Diesel/CNG)
   - Seller Type (Individual/Dealer)
   - Transmission Type (Manual/Automatic)

3. **Click "Predict Selling Price"** to get the estimated price

4. **View the result** displayed on the same page

## 📁 Project Structure

```
car-price-prediction/
│
├── app.py                                    # Flask application
├── random_forest_regression_model.pkl        # Trained model
├── requirements.txt                          # Python dependencies
│
├── templates/
│   └── index.html                           # Web interface
│
├── static/                                  # Static files (if needed)
│   ├── css/
│   └── js/
│
├── notebooks/
│   └── car_price_prediction.ipynb           # Jupyter notebook for model training
│
├── data/
│   └── car_data.csv                         # Dataset
│
├── README.md                                # Project documentation
└── .gitignore                               # Git ignore file
```

## 🧠 Model Details

### Algorithm

**Random Forest Regressor** - An ensemble learning method that operates by constructing multiple decision trees and outputting the mean prediction.

### Features Used

- **Present_Price**: Current showroom price
- **Kms_Driven**: Kilometers driven (log-transformed)
- **Owner**: Number of previous owners
- **Year**: Age of the car (calculated as 2020 - purchase year)
- **Fuel_Type**: Petrol or Diesel (one-hot encoded)
- **Seller_Type**: Individual or Dealer (one-hot encoded)
- **Transmission**: Manual or Automatic (one-hot encoded)

### Model Training Process

1. **Data Preprocessing**

   - Handle missing values
   - Remove outliers
   - Feature engineering (log transformation, age calculation)
   - One-hot encoding for categorical variables

2. **Exploratory Data Analysis**

   - Correlation analysis
   - Distribution plots
   - Feature importance using ExtraTreesRegressor

3. **Model Training**

   - Train-test split (80-20)
   - Random Forest Regressor training
   - Hyperparameter tuning with RandomizedSearchCV

4. **Model Evaluation**
   - R² Score
   - Mean Absolute Error (MAE)
   - Root Mean Squared Error (RMSE)
   - Residual analysis

### Hyperparameters

```python
n_estimators: [100, 200, 300, ..., 1200]
max_depth: [10, 20, 30, None]
min_samples_split: [2, 5, 10]
max_features: ['sqrt', 'log2']
```

## 🔮 Future Enhancements

- [ ] Add more features (brand, model, color, condition)
- [ ] Implement additional ML algorithms (XGBoost, Gradient Boosting)
- [ ] Create user authentication system
- [ ] Add prediction history tracking
- [ ] Deploy to cloud (Heroku, AWS, Azure)
- [ ] Develop REST API for integration
- [ ] Add data visualization dashboard
- [ ] Implement model retraining pipeline
- [ ] Mobile application version
- [ ] Real-time market data integration

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Your Name**

- GitHub: [@yourusername](https://github.com/yourusername)
- LinkedIn: [Your LinkedIn](https://linkedin.com/in/yourprofile)
- Email: your.email@example.com

## 🙏 Acknowledgments

- Dataset source: [Kaggle/UCI/Other]
- Inspiration from various car price prediction projects
- scikit-learn documentation
- Flask documentation
