# Student perfomance data  analysis Mozabique

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.0%2B-150458?style=for-the-badge&logo=pandas&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Complete-success?style=for-the-badge)

An exploratory data analysis (EDA) project examining factors that influence student academic performance using the UCI Machine Learning Repository dataset.

---

## 📋 Table of Contents

- [About The Project](#about-the-project)
- [Dataset](#dataset)
- [Research Questions](#research-questions)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Key Findings](#key-findings)
- [Visualizations](#visualizations)
- [Technologies Used](#technologies-used)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)
- [Acknowledgments](#acknowledgments)

---

## 🎯 About The Project

This project conducts a comprehensive Exploratory Data Analysis (EDA) on student performance data to identify key factors affecting academic outcomes. The analysis follows a Monitoring & Evaluation (M&E) framework to derive actionable insights for educational stakeholders.

### Objectives

- Identify factors that correlate with student academic performance
- Analyze the impact of family support on student grades
- Examine the relationship between attendance and academic outcomes
- Evaluate the influence of parental education on student success
- Assess how study time affects final grades

---

## 📊 Dataset

### Source
**UCI Machine Learning Repository - Student Performance Dataset**
- **Dataset ID:** 320
- **URL:** [UCI ML Repository](https://archive.ics.uci.edu/dataset/320/student+performance)

### Description
The dataset contains student achievement data from two Portuguese secondary schools. It includes student grades, demographic information, social factors, and school-related features.

### Features Overview

| Category | Variables |
|----------|-----------|
| **Demographics** | age, sex, address, famsize |
| **Family** | Medu, Fedu, Mjob, Fjob, guardian, famsup |
| **Education** | school, studytime, failures, schoolsup, activities |
| **Social** | freetime, goout, romantic, famrel |
| **Health** | health, absences |
| **Grades** | G1 (Period 1), G2 (Period 2), G3 (Final) |

### Dataset Statistics

| Metric | Value |
|--------|-------|
| Total Records | 649 |
| Total Features | 30+ |
| Target Variable | G3 (Final Grade) |
| Grade Scale | 0-20 |
| Pass Threshold | ≥ 10 |

---

## ❓ Research Questions

This analysis addresses the following key questions:

1. **Q1:** What factors most strongly correlate with final student performance (G3)?

2. **Q2:** Is there a performance gap between students who receive family support (famsup) and those who don't?

3. **Q3:** How does student attendance (absences) relate to their period grades (G1, G2, G3)?

4. **Q4:** Does mother's education level (Medu) impact student performance?

5. **Q5:** How does study time affect final grades?

---

## 📁 Project Structure

```
student-performance-analysis/
│
├── 📓 notebooks/
│   └── student_performance_analysis.ipynb    # Main analysis notebook
│
├── 📊 data/
│   ├── student_performance_RAW.csv           # Original uncleaned data
│   └── student_performance_CLEANED.csv       # Processed data
│
├── 📈 visualizations/
│   ├── grade_distribution.png
│   ├── correlation_heatmap.png
│   ├── family_support_analysis.png
│   └── absences_vs_grades.png
│
├── 📄 README.md                              # Project documentation
├── 📄 requirements.txt                       # Python dependencies
└── 📄 LICENSE                                # License file
```

---

## 🛠️ Installation

### Prerequisites

- Python 3.8 or higher
- Jupyter Notebook or JupyterLab
- pip package manager

### Step-by-Step Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/student-performance-analysis.git
   cd student-performance-analysis
   ```

2. **Create a virtual environment (recommended)**
   ```bash
   python -m venv venv
   
   # On Windows
   venv\Scripts\activate
   
   # On macOS/Linux
   source venv/bin/activate
   ```

3. **Install required packages**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

### Requirements.txt

```
pandas>=2.0.0
numpy>=1.24.0
matplotlib>=3.7.0
seaborn>=0.12.0
ucimlrepo>=0.0.3
jupyter>=1.0.0
openpyxl>=3.1.0
```

---

## 🚀 Usage

### Running the Analysis

1. Open `student_performance_analysis.ipynb` in Jupyter Notebook

2. Run all cells sequentially (Cell → Run All)

3. View generated visualizations and findings

### Quick Start

```python
# Install required package
!pip install ucimlrepo

# Import and load data
from ucimlrepo import fetch_ucirepo
import pandas as pd

# Fetch dataset
student_performance = fetch_ucirepo(id=320)

# Create dataframe
X = student_performance.data.features
y = student_performance.data.targets
df = pd.concat([X, y], axis=1)

# View first rows
df.head()
```

---

## 📈 Key Findings

### 1. Strongest Predictors of Performance

| Variable | Correlation with G3 | Interpretation |
|----------|---------------------|----------------|
| G2 | ~0.918548 | Previous grades are strongest predictor |
| G1 | ~0.826387 | First period grade highly predictive |
| Medu | ~0.24 | Mother's education has positive impact |
| failures | ~-0.39 | Past failures negatively impact grades |
| absences | ~-0.09 | More absences linked to lower grades |

### 2. Family Support Impact

- Students **with** family support show slightly different performance patterns
- Family educational support (famsup) has measurable impact on outcomes

### 3. Attendance Matters

- Negative correlation between absences and grades
- Students with 0 absences perform better on average
- High absence rates (11+) associated with lower performance

### 4. Parental Education Effect

- Higher mother's education (Medu) correlates with better student grades
- Students with university-educated mothers average higher G3 scores

### 5. Study Time Benefits

- More study time generally associated with better grades
- Diminishing returns observed at highest study levels

---

## 📊 Visualizations

The analysis includes various visualizations:

### Grade Distribution
![Grade Distribution](visualizations/grade_distribution.png)
*Distribution of final grades (G3) with pass/fail threshold*

### Correlation Heatmap
![Correlation Heatmap](visualizations/correlation_heatmap.png)
*Correlation matrix showing relationships between variables*

### Family Support Analysis
![Family Support](visualizations/family_support_analysis.png)
*Comparison of grades by family support status*

### Absences vs Grades
![Absences](visualizations/absences_vs_grades.png)
*Scatter plot showing relationship between absences and performance*

---

## 🛠️ Technologies Used

| Technology | Purpose |
|------------|---------|
| ![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white) | Programming Language |
| ![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white) | Data Manipulation |
| ![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white) | Numerical Computing |
| ![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C?style=flat) | Data Visualization |
| ![Seaborn](https://img.shields.io/badge/Seaborn-3776AB?style=flat) | Statistical Visualization |
| ![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=flat&logo=jupyter&logoColor=white) | Interactive Development |

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the Project**
   ```bash
   git fork https://github.com/yourusername/student-performance-analysis.git
   ```

2. **Create your Feature Branch**
   ```bash
   git checkout -b feature/AmazingFeature
   ```

3. **Commit your Changes**
   ```bash
   git commit -m 'Add some AmazingFeature'
   ```

4. **Push to the Branch**
   ```bash
   git push origin feature/AmazingFeature
   ```

5. **Open a Pull Request**

### Contribution Ideas

- [ ] Add machine learning models for prediction
- [ ] Create interactive dashboard with Plotly
- [ ] Add statistical hypothesis testing
- [ ] Include more visualizations
- [ ] Add data preprocessing pipeline

---

## 📜 License

Distributed under the MIT License. See `LICENSE` for more information.

```
MIT License

Copyright (c) 2024 [Your Name]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
```

---

## 📧 Contact

**Your Name**

- GitHub: [@PatPhade1985](https://github.com/PatPhade1985)
- LinkedIn: [Your LinkedIn](https://linkedin.com/in/yourprofile)
- Email: your.email@example.com

**Project Link:** [https://github.com/yourusername/student-performance-analysis](https://github.com/yourusername/student-performance-analysis)

---

## 🙏 Acknowledgments

- [UCI Machine Learning Repository](https://archive.ics.uci.edu/) - For providing the dataset
- [Paulo Cortez](http://www3.dsi.uminho.pt/pcortez/) - Original dataset creator
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Seaborn Documentation](https://seaborn.pydata.org/)
- [Matplotlib Documentation](https://matplotlib.org/stable/contents.html)

### Dataset Citation

```
P. Cortez and A. Silva. Using Data Mining to Predict Secondary School Student Performance. 
In A. Brito and J. Teixeira Eds., Proceedings of 5th FUture BUsiness TEChnology Conference 
(FUBUTEC 2008) pp. 5-12, Porto, Portugal, April, 2008, EUROSIS, ISBN 978-9077381-39-7.
```

---

## ⭐ Show Your Support

Give a ⭐️ if this project helped you!

---

<p align="center">
  Made with ❤️ and Python
</p>
```

---

# Additional Files to Create

## requirements.txt

```
pandas>=2.0.0
numpy>=1.24.0
matplotlib>=3.7.0
seaborn>=0.12.0
ucimlrepo>=0.0.3
jupyter>=1.0.0
openpyxl>=3.1.0
```

## .gitignore

```
# Byte-compiled files
__pycache__/
*.py[cod]
*$py.class

# Jupyter Notebook checkpoints
.ipynb_checkpoints/

# Virtual environment
venv/
env/
ENV/

# IDE
.vscode/
.idea/

# OS files
.DS_Store
Thumbs.db

# Data files (optional - remove if you want to include data)
# *.csv
# *.xlsx
```

---

# How to Use This README

1. **Replace placeholders:**
   - `yourusername` → Your GitHub username
   - `Your Name` → Your actual name
   - `your.email@example.com` → Your email
   - Update LinkedIn profile URL

2. **Add visualization images:**
   - Save your plots as PNG files
   - Create a `visualizations/` folder
   - Update image paths in README

3. **Customize findings:**
   - Update correlation values with actual results
   - Add specific statistics from your analysis

> 💡 **Tip:** Preview your README on GitHub or use a Markdown previewer before pushing!
