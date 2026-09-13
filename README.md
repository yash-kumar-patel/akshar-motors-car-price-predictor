# 🚗 Akshar Motors: Car Price Predictor

**Intelligent Second-Hand Vehicle Valuation System**

[![Live App](https://img.shields.io/badge/Live%20App-Streamlit-FF4B4B?style=for-the-badge&logo=streamlit)](https://akshar-car-price-predictor.streamlit.app)
[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

---

## 🎯 Project Overview

Akshar Motors is a machine learning-powered car price prediction system that estimates second-hand vehicle prices with high accuracy. The application combines data-driven valuation models with an intuitive web interface, enabling car dealerships and individual buyers to make informed pricing decisions instantly.

### The Problem
Pricing used cars manually is time-consuming and error-prone. The market volatility and numerous variables (age, mileage, brand, condition) make accurate valuations challenging.

### The Solution
This system trained on real market data uses Linear Regression to predict prices based on vehicle specifications, providing instant, data-backed valuations.

### Key Value Propositions
- ⚡ **Instant Valuations** - Get price predictions in seconds
- 📊 **Data-Driven** - Based on real market data and statistical models
- 🎨 **User-Friendly** - Interactive web interface requires no technical knowledge
- 🔧 **Transparent** - Clear feature inputs and interpretable predictions

---

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| **Interactive Web Interface** | User-friendly Streamlit app for price predictions |
| **Instant Valuations** | Real-time price estimation for any used vehicle |
| **Feature Engineering** | Optimized input variables for maximum prediction accuracy |
| **Model Pipeline** | Complete preprocessing and scaling pipeline |
| **Persistent Models** | Pre-trained models saved and ready for inference |

---

## 🛠️ Technology Stack

### Backend & ML
- **Python 3.8+** - Core language
- **Scikit-Learn** - Machine learning model and preprocessing
- **Pandas** - Data handling and feature preprocessing
- **NumPy** - Numerical computations

### Frontend & Deployment
- **Streamlit** - Interactive web application framework
- **Streamlit Cloud** - Hosting and deployment

### Development Tools
- **Git** - Version control
- **pip** - Dependency management

---

## 🏗️ Project Architecture

```
streamlit (User Interface)
        ↓
[Input Processing & Feature Engineering]
  - Feature scaling (StandardScaler)
  - Input validation
  - Feature encoding
        ↓
[Pre-trained ML Model]
  - Linear Regression model (car_price_model.pkl)
  - Feature columns (feature_columns.pkl)
  - Scaler (scaler.pkl)
        ↓
[Price Prediction Output]
```

---

## 📁 Project Structure

```
akshar-motors-car-price-predictor/
├── app.py                          # Streamlit application entry point
├── car_price_model.pkl             # Trained Linear Regression model
├── feature_columns.pkl             # Feature column names and metadata
├── scaler.pkl                      # StandardScaler for feature normalization
├── requirements.txt                # Python dependencies
├── .devcontainer/                  # Development container configuration
├── README.md                       # Project documentation
└── LICENSE                         # MIT License
```

### Key Files Explained

| File | Purpose |
|------|---------|
| `app.py` | Main Streamlit application with UI and prediction logic |
| `car_price_model.pkl` | Serialized pre-trained Linear Regression model |
| `feature_columns.pkl` | Feature metadata for consistent input processing |
| `scaler.pkl` | Fitted StandardScaler for feature normalization |
| `requirements.txt` | All required Python packages and versions |

---

## 🚀 Quick Start

### 1. Prerequisites
- Python 3.8 or higher
- pip (Python package manager)
- ~200MB disk space

### 2. Installation

```bash
# Clone the repository
git clone https://github.com/yashintelligence/akshar-motors-car-price-predictor.git
cd akshar-motors-car-price-predictor

# Create virtual environment (recommended)
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

### 3. Run Locally

```bash
# Start the Streamlit application
streamlit run app.py

# Application will open at: http://localhost:8501
```

### 4. Use the Live Application
Visit the live deployment: [Akshar Motors on Streamlit Cloud](https://akshar-car-price-predictor.streamlit.app)

---

## 📊 How It Works

### User Input
Users provide vehicle specifications:
- Brand/Make
- Model
- Year of manufacture
- Mileage
- Condition/Age
- Body type
- Fuel type
- Transmission

### Processing Pipeline
1. **Input Validation** - Ensure data integrity
2. **Feature Engineering** - Transform inputs to model-compatible format
3. **Feature Scaling** - Normalize using pre-fitted StandardScaler
4. **Model Inference** - Linear Regression prediction

### Output
- **Predicted Price** - Estimated market value in INR
- **Price Range** - Confidence interval
- **Explanation** - Key factors influencing the prediction

---

## 📈 Model Information

### Model Type
**Linear Regression** - Interpretable and reliable for price prediction

### Training Data
- Real second-hand car market data
- Multiple vehicle brands and categories
- Historical pricing patterns

### Model Performance
- Optimized for accuracy and interpretability
- Fast inference (< 100ms per prediction)
- Consistent predictions across varied inputs

### Feature Importance
The model considers:
- Vehicle age/year
- Mileage
- Brand reputation
- Condition metrics
- Market demand factors

---

## 🔧 Development

### Local Development Setup

```bash
# Install development dependencies
pip install -r requirements.txt
pip install black flake8 pytest  # Code quality tools (optional)

# Run linting
flake8 app.py

# Format code
black app.py
```

### Deployment to Streamlit Cloud

1. Push code to GitHub
2. Go to [Streamlit Cloud](https://streamlit.io/cloud)
3. Create new app from this repository
4. Connect and deploy

---

## 📦 Dependencies

```
streamlit>=1.28.0
pandas>=1.5.0
numpy>=1.23.0
scikit-learn>=1.3.0
```

Install all at once:
```bash
pip install -r requirements.txt
```

---

## 🤔 FAQ

**Q: How accurate are the predictions?**  
A: The model achieves strong performance on held-out test data. Accuracy depends on data quality and how closely the vehicle matches training data characteristics.

**Q: Can I use this for my own car pricing?**  
A: Yes! The app works for any used car. For best results, ensure your inputs match the training data range.

**Q: Is my data stored?**  
A: No. All predictions are processed client-side. No user data is stored or logged.

**Q: How often is the model updated?**  
A: Currently using a static pre-trained model. Contact for information about model retraining.

**Q: Can I deploy this myself?**  
A: Absolutely! Clone the repository and deploy to Streamlit Cloud, Heroku, or any Python-capable platform.

---

## 📚 Technical Details

### Model Pipeline
```python
# Simplified model flow
input_features → feature_engineering → scaling → [Linear Regression] → price_prediction
```

### Prediction Example
```python
# Sample input
vehicle = {
    'year': 2015,
    'mileage': 85000,
    'brand': 'Toyota',
    'condition': 'Good'
}

# Output
predicted_price = ₹450,000 (±₹30,000)
```

---

## 🔮 Future Improvements

- [ ] Add confidence intervals to predictions
- [ ] Implement more advanced models (XGBoost, Neural Networks)
- [ ] Add historical price trend analysis
- [ ] Integrate real market data API for model updates
- [ ] Add model explainability features (SHAP, LIME)
- [ ] Create API endpoint for programmatic access
- [ ] Add multi-currency support
- [ ] Implement A/B testing framework for model updates

---

## 📝 License

This project is licensed under the MIT License - see [LICENSE](LICENSE) file for details.

---

## 🤝 Contributing

Contributions are welcome! Please feel free to:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/improvement`)
3. Make your changes
4. Test thoroughly
5. Commit with clear messages (`git commit -m 'Add feature'`)
6. Push to your branch (`git push origin feature/improvement`)
7. Open a Pull Request

For major changes, please open an issue first to discuss proposed changes.

---

## 🐛 Reporting Issues

Found a bug? Have a suggestion? Please open an [issue](https://github.com/yashintelligence/akshar-motors-car-price-predictor/issues) with:
- Clear description of the problem
- Steps to reproduce (if applicable)
- Expected vs. actual behavior
- System information (Python version, OS, etc.)

---

## 👤 About the Author

**Yash Kumar Patel**  
Data Scientist | Machine Learning Engineer  
📧 [Email](mailto:yashakshar31@gmail.com) | 🔗 [LinkedIn](https://www.linkedin.com/in/yash-kumar-patel/) | 🐙 [GitHub](https://github.com/yashintelligence)

---

## 🙏 Acknowledgments

- Built with [Streamlit](https://streamlit.io/) - Amazing framework for data apps
- Powered by [Scikit-Learn](https://scikit-learn.org/) - Industry-standard ML library
- Data processing with [Pandas](https://pandas.pydata.org/) - The data manipulation legend

---

<div align="center">

Made with 💛 by Yash Patel

⭐ Found this helpful? Please star the repository!

</div>
