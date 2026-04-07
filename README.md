# Network Intrusion Detection using Ensemble Learning

An AI-powered Intrusion Detection System (IDS) designed to classify network traffic as **Benign** or **Malicious**. This project implements a full machine learning pipeline, from raw log processing and behavioral feature engineering to optimized ensemble modeling.

## 🚀 Overview
Traditional security systems often miss novel "zero-day" attacks. This project leverages **Ensemble Learning** (Random Forest, XGBoost) and **SMOTE** (Synthetic Minority Over-sampling Technique) to detect anomalies in highly imbalanced network data (96% benign vs. 4% attack).

### Key Features:
- **Behavioral Feature Engineering**: Extracts signals from URLs (length, special characters) and User-Agent strings (bot detection).
- **Imbalance Handling**: Uses SMOTE to handle the extreme 96:4 class distribution.
- **Optimized Performance**: Achieved a **97.7% Cross-Validation F1-Score** using hyperparameter-tuned Random Forest.
- **Syllabus Alignment**: Maps core ML concepts (Classification, Ensembles, Evaluation) to a real-world cybersecurity use case.

---

## 📂 Project Structure
```text
├── data/                   # Dataset (cybersecurity.csv)
├── src/                    # Implementation scripts
│   ├── baseline_ids.py     # Initial models (Logistic Regression, KNN, SVM)
│   ├── ids_enhanced.py     # Added Feature Engineering & SMOTE
│   └── ids_final_optimized.py # Final GridSearchCV & Cross-Validation
├── outputs/                # Visualizations & Metrics (Plots, JSON results)
├── presentation/           # Materials for project walkthrough
├── Project_Report.md       # Comprehensive technical documentation
├── Project_Mapping.md      # Mapping project to ML syllabus
└── predict_custom.py       # Script for testing on new/custom data
```

---

## 🛠️ Installation & Usage

### 1. Setup Environment
```bash
# Create and activate virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install pandas numpy matplotlib seaborn scikit-learn xgboost imbalanced-learn
```

### 2. Run the Pipeline
To train the final optimized model and generate results:
```bash
python src/ids_final_optimized.py
```

### 3. Test with Custom Data
You can use the `predict_custom.py` script to test the model against specific network logs:
```bash
python predict_custom.py
```

---

## 📊 Results
The final **Random Forest** model was selected after comparing multiple architectures.
- **Accuracy**: 96.0%
- **CV F1-Score**: 97.7%
- **Key Indicators**: `url_special_chars`, `url_length`, and `is_bot` were the most significant features for identifying malicious intent.

Visualizations for Feature Importance and Confusion Matrices can be found in the `outputs/` directory.

---

## 📝 Documentation
- **[Technical Report](Project_Report.md)**: Detailed methodology, EDA, and result analysis.
- **[Syllabus Mapping](Project_Mapping.md)**: How this project covers ML modules (Ensembles, Entropy, Bias-Variance, etc.).
- **[Presentation Guide](presentation/Presentation_Guide.md)**: Summary for viva/presentation.

---
**Course:** Machine Learning [CSE-4408]  
**Topic:** Ensemble Learning in Cybersecurity
