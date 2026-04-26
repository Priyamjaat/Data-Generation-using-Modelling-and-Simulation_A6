# Data-Generation-using-Modelling-and-Simulation_A6
# 📊 TOPSIS-Based Model Selection

This project implements the **TOPSIS (Technique for Order Preference by Similarity to Ideal Solution)** method to rank and select the best alternative based on multiple criteria.

🔗 GitHub Repository: https://github.com/Priyamjaat/Topsis_For_Pre

---

## 🚀 Objective
To apply TOPSIS for **multi-criteria decision making** and rank alternatives (e.g., ML models) based on performance metrics.

---

## 📂 Files Included
```
├── topsis.py                        # Python implementation
├── topsis_model_selection.ipynb     # Main notebook (assignment)
├── ml_model_comparison.ipynb        # Model comparison
├── football_simulation.ipynb        # Extra notebook
├── data.csv                         # Input dataset
└── README.md                        # Documentation
```

---

## 🧠 Methodology (Step-by-Step)

### 1. Decision Matrix
- Input data is taken from a CSV file  
- Rows → Alternatives (e.g., ML models)  
- Columns → Criteria (e.g., accuracy, time, etc.)

---

### 2. Normalization
Each value is normalized using:

\[
r_{ij} = \frac{x_{ij}}{\sqrt{\sum x_{ij}^2}}
\]

---

### 3. Weighted Normalization
Each column is multiplied by its respective weight:

\[
v_{ij} = w_j \cdot r_{ij}
\]

---

### 4. Ideal Best & Worst
- **Ideal Best (A⁺)** → Max for benefit, Min for cost  
- **Ideal Worst (A⁻)** → Opposite  

---

### 5. Distance Calculation
\[
S_i^+ = \sqrt{\sum (v_{ij} - A_j^+)^2}
\]

\[
S_i^- = \sqrt{\sum (v_{ij} - A_j^-)^2}
\]

---

### 6. TOPSIS Score
\[
C_i = \frac{S_i^-}{S_i^+ + S_i^-}
\]

---

### 7. Ranking
- Higher score = Better alternative  
- Rank assigned accordingly  

---

## ▶️ How to Run

### Using Python Script
```bash
python topsis.py data.csv "1,1,1,1" "+,+,-,+" result.csv
```

### Using Notebook
```bash
jupyter notebook topsis_model_selection.ipynb
```

---

## 📥 Input Format
- CSV file with ≥ 3 columns  
- First column → Non-numeric  
- Remaining → Numeric  

### Example:
```
Model,Accuracy,Precision,Time,Error
A,0.91,0.89,120,0.09
B,0.88,0.85,100,0.12
C,0.93,0.90,140,0.07
```

---

## ⚖️ Parameters

### Weights
- Importance of each criterion  
- Example: `"1,2,1,1"`

### Impacts
- `+` → Benefit criteria  
- `-` → Cost criteria  
- Example: `"+,+,-,-"`

---

## 📊 Result Table

| Model | Score | Rank |
|------|------|------|
| A    | 0.65 | 2    |
| B    | 0.52 | 3    |
| C    | 0.78 | 1    |

👉 Model **C** is the best choice.

---

## 📈 Result Graph

A graph is plotted in the notebook showing:
- X-axis → Alternatives  
- Y-axis → TOPSIS Score  

### Interpretation:
- Higher bar = Better performance  
- Clearly shows ranking visually  

---

## 📊 Observations
- Models with higher accuracy and lower error rank better  
- Weight selection significantly affects results  
- TOPSIS provides a balanced decision-making approach  

---

## ❌ Error Handling
- Invalid file path  
- Non-numeric values  
- Mismatch in weights & impacts  
- Invalid symbols  

---

## 💡 Applications
- Machine Learning model selection  
- Product comparison  
- Business decision-making  
- Ranking systems  

---

## 🛠️ Tech Stack
- Python  
- Pandas  
- NumPy  
- Matplotlib (for graphs)

---

## 👨‍💻 Author
**Priyam Chaudhary**

---

## ⭐ Note
This project is part of an academic assignment and demonstrates the implementation of TOPSIS for decision-making problems.
