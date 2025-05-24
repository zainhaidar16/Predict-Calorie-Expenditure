# 🔥 Calorie Expenditure Prediction Project

A comprehensive machine learning project that predicts calorie expenditure based on physical and exercise-related features using multiple regression models.

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Latest-orange)](https://scikit-learn.org/)
[![XGBoost](https://img.shields.io/badge/XGBoost-Latest-green)](https://xgboost.readthedocs.io/)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue)](LICENSE)

## 📋 Table of Contents

- [Project Overview](#-project-overview)
- [Features](#-features)
- [Dataset Description](#-dataset-description)
- [Models Implemented](#-models-implemented)
- [Project Structure](#-project-structure)
- [Setup Instructions](#️-setup-instructions)
- [Usage](#-usage)
- [Model Performance](#-model-performance)
- [Key Insights](#-key-insights)
- [Evaluation Metrics](#-evaluation-metrics)
- [Visualizations](#-visualizations)
- [Contributing](#-contributing)
- [License](#-license)

## 🎯 Project Overview

This project aims to predict calorie expenditure during physical activities using machine learning techniques. The analysis includes comprehensive data exploration, feature engineering, model comparison, and performance evaluation using multiple regression algorithms.

### Key Objectives

- **Predict calorie expenditure** based on personal and exercise characteristics
- **Compare performance** of different machine learning models
- **Identify key factors** that influence calorie burning
- **Provide insights** for fitness and health applications

## ✨ Features

- **Comprehensive Data Analysis**: Complete exploratory data analysis with statistical insights
- **Multiple ML Models**: Implementation of Random Forest, XGBoost, and Ridge Regression
- **Advanced Evaluation**: Uses multiple metrics including RMSLE, MAE, RMSE, R², and MAPE
- **Feature Importance Analysis**: Identifies the most influential factors for calorie prediction
- **Cross-Validation**: Robust model evaluation using 5-fold cross-validation
- **Professional Visualizations**: Beautiful charts and plots for data insights
- **Automated Model Selection**: Identifies the best performing model automatically

## 📊 Dataset Description

The dataset contains information about individuals and their exercise sessions:

### Input Features

- **Personal Characteristics**:
  - `Age`: Age of the individual (years)
  - `Sex`: Gender (male/female)
  - `Height`: Height in centimeters
  - `Weight`: Weight in kilograms

- **Exercise Metrics**:
  - `Duration`: Exercise duration (minutes)
  - `Heart_Rate`: Average heart rate during exercise (bpm)
  - `Body_Temp`: Body temperature during exercise (°C)

### Target Variable

- **`Calories`**: Total calories burned during the exercise session

### Dataset Statistics

- **Training samples**: 750,000 records
- **Test samples**: 250,000 records
- **Features**: 7 input features + 1 target variable
- **Data quality**: No missing values, clean dataset

## 🤖 Models Implemented

### 1. Random Forest Regressor 🌲

- **Type**: Ensemble method using multiple decision trees
- **Strengths**: Robust to overfitting, handles mixed data types well
- **Hyperparameters**: 200 estimators, max depth 15, optimized splits

### 2. XGBoost Regressor 🚀

- **Type**: Gradient boosting framework
- **Strengths**: Superior performance, handles complex patterns
- **Hyperparameters**: 200 estimators, learning rate 0.1, regularization parameters

### 3. Ridge Regression 📏

- **Type**: Linear regression with L2 regularization
- **Strengths**: Simple, interpretable, good baseline
- **Hyperparameters**: Alpha=1.0, regularization to prevent overfitting

## 📁 Project Structure

```

Predict-Calorie-Expenditure/
│
├── 📊 Data Files
│   ├── train.csv                          # Training dataset
│   ├── test.csv                           # Test dataset (for predictions)
│   └── calorie_predictions.csv            # Generated predictions
│
├── 📓 Notebooks & Code
│   └── predict_calorie_expenditure.ipynb  # Main analysis notebook
│
├── ⚙️ Configuration
│   ├── requirements.txt                   # Python dependencies
│   └── env/                              # Virtual environment
│
├── 📖 Documentation
│   ├── README.md                         # This file
│   └── LICENSE                           # Apache License 2.0
│
└── 🔄 Environment
    └── env/                              # Python virtual environment
        ├── Scripts/                      # Environment executables
        ├── Lib/                         # Installed packages
        └── pyvenv.cfg                   # Environment configuration
```

## 🛠️ Setup Instructions

### Prerequisites

- Python 3.8 or higher
- Git (for cloning the repository)
- 8GB+ RAM recommended for large dataset processing

### Step 1: Clone the Repository

```powershell
git clone https://github.com/zainhaidar16/Predict-Calorie-Expenditure.git
cd Predict-Calorie-Expenditure
```

### Step 2: Create Virtual Environment

```powershell
# Create virtual environment
python -m venv env

# Activate the environment
.\env\Scripts\Activate.ps1

# If execution policy prevents activation, run:
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

### Step 3: Install Dependencies

```powershell
# Install all required packages
pip install -r requirements.txt

# Verify installation
pip list
```

### Step 4: Launch Jupyter Notebook

```powershell
# Start Jupyter
jupyter notebook

# Or use Jupyter Lab
jupyter lab
```

### Step 5: Run the Analysis

1. Open `predict_calorie_expenditure.ipynb` in Jupyter
2. Run all cells sequentially (Cell → Run All)
3. View results and visualizations

### Alternative: Quick Setup Script

```powershell
# All-in-one setup (run in PowerShell)
python -m venv env
.\env\Scripts\Activate.ps1
pip install -r requirements.txt
jupyter notebook
```

## 🚀 Usage

### Running the Complete Analysis

```python
# The notebook is organized in sections:
# 1. Data Loading and Exploration
# 2. Data Cleaning and Preprocessing  
# 3. Exploratory Data Analysis
# 4. Feature Engineering
# 5. Model Training and Evaluation
# 6. Model Comparison and Selection
```

### Key Functions in the Notebook

#### Model Evaluation Function

```python
def evaluate_model(y_true, y_pred, model_name):
    """Calculate comprehensive evaluation metrics including RMSLE"""
    # Returns: MAE, RMSE, R², MAPE, RMSLE
```

#### Cross-Validation Analysis

```python
# 5-fold cross-validation for robust performance estimation
cv_scores = cross_val_score(model, X, y, cv=5, scoring='r2')
```

## 📈 Model Performance

### Performance Comparison

| Model | MAE | RMSE | R² Score | MAPE (%) | RMSLE |
|-------|-----|------|----------|----------|--------|
| **XGBoost** ⭐ | 2.18 | 3.60 | **0.9966** | 3.84 | **0.0374** |
| Random Forest | 2.24 | 3.74 | 0.9964 | 3.85 | 0.0382 |
| Ridge Regression | 8.08 | 11.06 | 0.9684 | 28.71 | 0.1247 |

### 🏆 Best Model: XGBoost

- **Highest R² Score**: 99.66% variance explained
- **Lowest RMSE**: 3.60 calories average error
- **Best RMSLE**: 0.0374 (excellent for this regression task)
- **Consistent Performance**: Robust across cross-validation folds

## 🔍 Key Insights

### Most Important Features (from XGBoost)

1. **Duration** (85.05%): Exercise duration is the strongest predictor
2. **Heart Rate** (8.62%): Higher heart rates correlate with more calories burned
3. **Body Temperature** (2.65%): Elevated body temperature indicates increased metabolic activity
4. **Age** (1.77%): Age affects metabolic rate and calorie expenditure
5. **Sex** (1.48%): Gender influences base metabolic rate

### Feature Correlations

- **Duration ↔ Calories**: 0.96 (very strong positive correlation)
- **Heart Rate ↔ Calories**: 0.91 (strong positive correlation)
- **Body Temperature ↔ Calories**: 0.83 (strong positive correlation)

### Statistical Insights

- **Average Calories Burned**: 88.3 ± 62.4 calories per session
- **Duration Range**: 1-30 minutes (average: 15.4 minutes)
- **Heart Rate Range**: 67-136 bpm (average: 95.5 bpm)

## 📊 Evaluation Metrics

The project uses multiple evaluation metrics for comprehensive model assessment:

### Regression Metrics

- **MAE (Mean Absolute Error)**: Average absolute difference between predictions and actual values
- **RMSE (Root Mean Square Error)**: Square root of average squared differences (penalizes large errors)
- **R² Score**: Proportion of variance explained by the model (higher is better)
- **MAPE (Mean Absolute Percentage Error)**: Average percentage error
- **RMSLE (Root Mean Squared Logarithmic Error)**: Logarithmic error metric, robust to outliers

### Cross-Validation

- **5-Fold CV**: Ensures robust performance estimates
- **Consistent Results**: Low standard deviation across folds indicates stable models

## 🎨 Visualizations

The notebook includes comprehensive visualizations:

### Data Exploration

- **Distribution plots** for all features
- **Correlation heatmaps** showing feature relationships
- **Target variable analysis** with statistical summaries

### Model Analysis

- **Feature importance charts** for tree-based models
- **Performance comparison plots** across all metrics
- **Prediction vs Actual scatter plots** for model validation
- **Cross-validation box plots** showing model stability

### Statistical Analysis

- **Q-Q plots** for normality testing
- **Box plots** for outlier detection
- **Pair plots** for feature relationships

## 🔮 Future Enhancements

### Potential Improvements

- **Advanced Feature Engineering**: Create interaction features, polynomial terms
- **Hyperparameter Tuning**: Grid search or Bayesian optimization
- **Ensemble Methods**: Combine multiple models for better performance
- **Deep Learning**: Neural networks for complex pattern recognition
- **Time Series Analysis**: If temporal data becomes available

### Additional Features

- **Model Deployment**: REST API for real-time predictions
- **Web Interface**: User-friendly web application
- **Mobile App**: Fitness tracking integration
- **Real-time Monitoring**: Live calorie prediction during workouts

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

### How to Contribute

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Areas for Contribution

- Model improvements and new algorithms
- Additional visualizations and analysis
- Code optimization and refactoring
- Documentation enhancements
- Bug fixes and testing

## 📄 License

This project is licensed under the Apache License 2.0 - see the [LICENSE](LICENSE) file for details.

### Apache License 2.0 Summary:

- ✅ **Commercial use**: You can use this code for commercial purposes
- ✅ **Modification**: You can modify the code
- ✅ **Distribution**: You can distribute the code
- ✅ **Patent use**: Express grant of patent rights from contributors
- ✅ **Private use**: You can use the code privately
- ⚠️ **License and copyright notice**: Must include license and copyright notice
- ⚠️ **State changes**: Must document changes made to the code

### Key Benefits of Apache License 2.0:

- **Business-friendly**: Allows commercial use without restrictions
- **Patent protection**: Provides explicit patent grants from contributors
- **Contributor protection**: Clear terms for contributions and liability
- **Flexibility**: Compatible with many other licenses

## 🏅 Acknowledgments

- **Scikit-Learn**: For comprehensive machine learning tools
- **XGBoost**: For the powerful gradient boosting framework
- **Matplotlib & Seaborn**: For beautiful data visualizations
- **Pandas & NumPy**: For efficient data manipulation
- **Jupyter**: For the interactive development environment

## 📞 Contact

For questions, suggestions, or collaboration opportunities:

- **Project Repository**: [GitHub Link](https://github.com/zainhaidar16/Predict-Calorie-Expenditure)
- **Issues**: Please use GitHub Issues for bug reports and feature requests

---

**⭐ If you found this project helpful, please consider giving it a star!**
