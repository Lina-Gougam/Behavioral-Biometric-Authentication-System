# Behavioral Biometric Authentication System

> A security project that uses behavioral biometrics—touchscreen gestures, keystroke dynamics, and mouse movement patterns—to continuously authenticate users.

**Course:** Computer & Network Security  
**Institution:** ENSIA  
**Year:** 3rd Year, Semester 2

---

## Project Overview

This project implements behavioral biometric authentication—a way to identify users based on how they interact with devices. Unlike passwords that you enter once, behavioral biometrics work continuously by analyzing typing speed, touch patterns, and mouse movements to catch if someone unauthorized is using the system.

### Key Features

- **Touchscreen Gesture Analysis** - 912,133 touch events from 5 users across 41 sessions
- **Keystroke Dynamics** - Typing pattern recognition for desktop authentication
- **Mouse Movement Patterns** - Cursor behavior analysis
- **Advanced ML Models** - Isolation Forest & One-Class SVM for anomaly detection
- **Interactive Demos** - Web-based and Jupyter interfaces for real-time testing
- **Comprehensive Metrics** - FAR, FRR, EER, and AUC-ROC evaluation

---

## Project Structure

```
Behavioral Biometric Authentication System/
├── README.md                                    # This file
├── video_link.md                               # Demo video link
├── behavioral_biometrics_slides.pdf            # Project presentation
├── Behavioral_Biometric_Authentication_Report (3).pdf  # Detailed report
├── Keystrocke_Mouse_Mouvment.rar              # Keystroke & mouse data
├── .vscode/                                    # VS Code configuration
├── touch screen/                               # Touchscreen biometrics module
│   ├── P003_Touchscreen_Biometrics_FINAL.ipynb    # Main analysis notebook
│   └── p003-demo (1).html                         # Interactive web demo
└── UI/                                         # Desktop UI (keystroke & mouse)
    ├── run_ui.py                               # Flask application entry point
    ├── requirements.txt                        # Python dependencies
    └── ...                                     # Additional modules
```

---

## Getting Started

### Prerequisites

- **Python 3.8+**
- **pip** or **conda** (package manager)
- **Modern web browser** (Chrome, Firefox, Edge)
- **Jupyter Notebook** (for notebook analysis)

### Installation Steps

#### Step 1: Clone/Download the Project
```bash
cd "path/to/Behavioral Biometric Authentication System"
```

#### Step 2: Install Dependencies

**For Touchscreen Analysis (Jupyter Notebook):**
```bash
pip install numpy pandas matplotlib seaborn scikit-learn
```

**For Desktop UI (Keystroke & Mouse Movement):**
```bash
cd UI
pip install flask flask-cors scipy scikit-learn joblib
```

---

## Running the Demos

### 1. Touchscreen Gesture Demo (Web-Based)

Test the touchscreen gesture recognition directly in your browser:

```bash
# Navigate to touch screen folder
cd "touch screen"

# Open the HTML file in your browser
# Option A: Double-click p003-demo (1).html
# Option B: Open with live server (if using VS Code extension)
# Option C: Use command line
start "p003-demo (1).html"  # Windows
open "p003-demo (1).html"   # macOS
```

**Features:**
- Draw touchscreen gestures on the canvas
- Real-time gesture analysis
- User authentication simulation
- Performance metrics display

---

### 2. Keystroke & Mouse Movement UI (Flask Web App)

This is where you can test keystroke and mouse movement analysis:

```bash
# Navigate to UI directory
cd UI

# Install required packages (if not already done)
pip install flask flask-cors scipy scikit-learn joblib

# Start the Flask application
python run_ui.py

# Open browser and navigate to
# http://127.0.0.1:5000
```

**Features:**
- Keystroke dynamics analysis (timing, pressure)
- Mouse movement pattern recognition
- Continuous authentication monitoring
- Real-time user verification

---

### 3. Touchscreen Analysis Notebook

Dive into the full analysis with this Jupyter notebook (data analysis, model training, evaluation):

```bash
# Navigate to touch screen folder
cd "touch screen"

# Launch Jupyter Notebook
jupyter notebook P003_Touchscreen_Biometrics_FINAL.ipynb
```

**Notebook Sections:**
1. Setup & Imports
2. Data Loading & Exploration
3. Exploratory Data Analysis (EDA)
4. Feature Engineering (19 features per gesture)
5. User Profiling & Train/Test Split
6. Anomaly Detection Model Training
7. FAR & FRR Threshold Analysis
8. ROC, EER, and Confusion Matrix Evaluation
9. Results Summary & Conclusions

---

## Technical Details

### Touchscreen Biometrics Dataset

| Metric | Value |
|--------|-------|
| Total Touch Events | 912,133 |
| Users | 5 |
| Sessions | 41 |
| Features per Gesture | 19 |
| Training Data | 80% |
| Testing Data | 20% |

### Anomaly Detection Models

- **Isolation Forest**: Works by isolating abnormal observations; if a behavior doesn't fit the normal pattern, it gets flagged
- **One-Class SVM**: Learns what normal user behavior looks like, then flags anything outside that boundary

### Evaluation Metrics

- **FAR** (False Acceptance Rate): How often an attacker gets in (lower is better)
- **FRR** (False Rejection Rate): How often a real user gets locked out (lower is better)
- **EER** (Equal Error Rate): The sweet spot where FAR and FRR are equal
- **AUC-ROC**: Shows overall accuracy of the system

---

## Video Demonstration

Want to see everything in action? Check out the full demo:

**[Watch Demo Video](https://youtu.be/3AqINGBOBWQ)**

The video covers:
- System architecture overview
- Demo of each authentication method
- Real-time performance metrics
- Comparative analysis of techniques

---

## Documentation Files

| File | Description |
|------|-------------|
| `behavioral_biometrics_slides.pdf` | Comprehensive presentation slides |
| `Behavioral_Biometric_Authentication_Report.pdf` | Detailed technical report with methodology and results |
| `Keystrocke_Mouse_Mouvment.rar` | Compressed dataset for keystroke and mouse analysis |
| `P003_Touchscreen_Biometrics_FINAL.ipynb` | Complete analysis and modeling code |

---

## Security Considerations

### Why It Works

- **Continuous checking** - Not just at login, but ongoing throughout the session
- **Hard to fake** - Your typing speed and touch patterns are uniquely yours
- **Invisible to users** - Doesn't interrupt the normal workflow
- **Stackable** - Can layer this on top of passwords or other methods

### Known Issues

- **Behavior changes** - Your typing might be different when you're tired or stressed
- **Device matters** - The system might perform differently on a phone vs. tablet
- **False rejections** - Sometimes legitimate users get locked out if their behavior varies  

---

## Troubleshooting

### Flask App Won't Start

```bash
# Ensure you're in the UI directory
cd UI

# Check Python version
python --version  # Should be 3.8 or higher

# Try with explicit Python module
python -m flask run

# Check if port 5000 is available
# If blocked, modify run_ui.py to use different port
```

### Jupyter Notebook Won't Load

```bash
# Ensure Jupyter is installed
pip install jupyter

# Launch from correct directory
cd "touch screen"
jupyter notebook

# If still issues, try updating
pip install --upgrade jupyter
```

### Missing Dependencies

```bash
# Reinstall all requirements
pip install --upgrade numpy pandas matplotlib seaborn scikit-learn scipy flask flask-cors joblib
```

---

## What You'll Learn

Working through this project covers:

- How behavioral biometrics actually work in practice
- How to extract useful features from raw biometric data
- Anomaly detection (using Isolation Forest and One-Class SVM)
- How to measure if an authentication system is good (FAR, FRR, EER)
- Building real-time authentication systems
- Flask for web applications
- Data analysis with Python (Jupyter, scikit-learn)

---

## References & Standards

- **NIST Guidelines**: Special Publication 800-63B (Authentication and Lifecycle Management)
- **Behavioral Biometrics**: Keystroke dynamics, touchscreen gestures, mouse movement
- **Machine Learning**: Scikit-learn documentation for anomaly detection algorithms
- **Security**: ISO/IEC 27001 Information Security Management

---

## Tips for Using the System

1. **Testing**: Try to use the same gestures and typing patterns each time—the system gets better when it learns your normal behavior
2. **Understanding the code**: The Jupyter notebook shows exactly how features are extracted from raw data
3. **Extending it**: The Flask code is clean and modular, so adding new types of biometrics shouldn't be too hard
4. **Real-world use**: If you actually deploy this, make sure to secure your trained models and use proper access controls

---

## Troubleshooting & Questions

Having trouble with something? Here's where to look:

- **Touchscreen issues**: The Jupyter notebook (cells 1-9) shows how the feature extraction works
- **Desktop UI problems**: Check the Flask route handlers in `run_ui.py`
- **Dataset questions**: Decompress `Keystrocke_Mouse_Mouvment.rar` to see the raw data
- **Methodology**: The PDF report has all the theory and technical details

---

## Before You Start

Make sure you have:

- [ ] Python 3.8 or higher
- [ ] All dependencies installed
- [ ] The project files downloaded
- [ ] Tested the touchscreen demo
- [ ] Tested the Flask UI
- [ ] Looked through the Jupyter notebook
- [ ] Watched the demo video

---

Status: Complete and Ready for Use  
Last Updated: 2026  
Security Level: Educational Project

---

*This project demonstrates advanced concepts in behavioral biometric authentication suitable for security research and educational purposes.*
