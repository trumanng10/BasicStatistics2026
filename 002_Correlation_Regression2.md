Alright Truman — statistician hat on 🎓
Based strictly on **PDF 2.01 → 2.08**, I’ll give you **3 solid, exam-ready use cases**, each tied to the **right statistical concept**, with **tables + graphs (conceptual illustrations)** and **clear interpretation**.
I’ll also tell you *why* each method is used — this is where marks usually hide.

---

## **Use Case 1: Lifestyle & Health Analysis**

### *(Crosstabs, Scatterplots, Pearson’s r)*

**Source concepts:** 2.01, 2.02

### **Research Question**

> Is chocolate consumption associated with body weight?

### **Variables**

| Variable              | Type        | Measurement                     |
| --------------------- | ----------- | ------------------------------- |
| Chocolate consumption | Independent | g/week (ordinal → quantitative) |
| Body weight           | Dependent   | kg                              |

---

### **Step 1: Crosstab (Ordinal View)**

Used **before** correlation to *discover patterns*.

| Body Weight ↓ / Chocolate → | <50g | 50–150g | >150g |
| --------------------------- | ---: | ------: | ----: |
| <50kg                       |  45% |     12% |    2% |
| 50–69kg                     |  38% |     40% |   18% |
| 70–89kg                     |  12% |     38% |   24% |
| ≥90kg                       |   5% |     10% |   56% |

**Interpretation**

* Higher chocolate intake → higher proportion of high body weight
* Crosstabs **show direction**, not strength

---

### **Step 2: Scatterplot (Quantitative View)**

**Why scatterplot first?**

* Checks **linearity**
* Detects **outliers**
* Decides if Pearson’s r is valid

---

### **Step 3: Pearson’s r**

* Result (example): **r = +0.93**
* Interpretation:

  * **Positive** → more chocolate, higher weight
  * **Strong** → points tightly cluster around line
  * **Linear** → Pearson’s r is appropriate

📌 **Exam Tip:**

> Pearson’s r tells **direction + strength**, *not causality*

---

## **Use Case 2: National Performance & Prediction**

### *(Regression Line, Equation, Prediction, R²)*

**Source concepts:** 2.03, 2.04, 2.05

### **Research Question**

> Can chocolate consumption predict Nobel Prize winners?

### **Variables**

| Variable                        | Role            |
| ------------------------------- | --------------- |
| Chocolate consumption (kg/year) | Independent (X) |
| Nobel laureates per 10m         | Dependent (Y)   |

---

### **Step 1: Scatterplot + Regression Line**

* Pearson’s r ≈ **0.93**
* Strong positive linear pattern

---

### **Step 2: Regression Equation**

[
\hat{y} = a + bx
]

Example from PDF:
[
\hat{y} = -5.63 + 2.80x
]

| Component     | Meaning                                        |
| ------------- | ---------------------------------------------- |
| **b = 2.80**  | Each extra kg chocolate → +2.8 Nobel winners   |
| **a = −5.63** | Mathematical intercept (no real-world meaning) |

---

### **Step 3: Prediction Example**

If a country consumes **6 kg/year**:
[
\hat{y} = -5.63 + (2.8 × 6) ≈ 11
]

📌 **Key Concept**
Regression allows **prediction**, correlation does not.

---

### **Step 4: Model Quality (R²)**

| Metric | Value | Meaning                   |
| ------ | ----- | ------------------------- |
| r      | 0.83  | Strong correlation        |
| R²     | 0.69  | 69% of variance explained |

![Image](https://bookdown.org/jdholster1/5403/rsquared2.png)

![Image](https://web.pdx.edu/~newsomj/pa551/Image278.gif)

**Interpretation**

* Regression predicts **69% better than using the mean**
* Remaining 31% = unexplained factors

---

## **Use Case 3: Social Attitudes & Misinterpretation Risk**

### *(Contingency Tables + Correlation ≠ Causation)*

**Source concepts:** 2.06, 2.07

### **Research Question**

> Are lower-educated people more likely to believe in extraterrestrial life?

---

### **Contingency Table (Column %)**

| Belief ↓ / Education → | Low | Middle | High |
| ---------------------- | --: | -----: | ---: |
| Agree                  | 12% |    25% |  50% |
| Disagree               | 63% |    50% |  16% |

**Correct Interpretation**

* Higher education → *more* belief
* Raw counts would mislead → percentages are essential

---

### **Why NOT Pearson’s r?**

| Reason            | Explanation             |
| ----------------- | ----------------------- |
| Measurement level | Ordinal variables       |
| Shape             | Non-quantitative        |
| Correct tool      | Crosstabs + percentages |

---

### **Correlation ≠ Causation (Critical Thinking)**

Possible explanations:

1. Education → openness to scientific ideas
2. Third variable (e.g., exposure to science media)
3. Reverse causality impossible → belief doesn’t change education

📌 **A+ Insight**

> Regression assumes explanation, but **never proves causality**

---

## **Summary Table (Exam-Friendly)**

| Use Case             | Method                 | Purpose                      |
| -------------------- | ---------------------- | ---------------------------- |
| Health behavior      | Crosstab → Pearson’s r | Detect & measure association |
| National performance | Regression + R²        | Predict & evaluate model     |
| Social attitudes     | Contingency table      | Avoid false causal claims    |

---

If you want next:

* 🔹 **Turn these into MBA exam answers**
* 🔹 **Convert into SPSS / SmartPLS workflow**
* 🔹 **Rewrite as A+ distinction-level discussion**

Just tell me which angle you want 😏
