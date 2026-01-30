
###Graph Used: https://colab.research.google.com/drive/1Q2xRdY2QxqpmrROzP0Mw8XXpWuZJwrHV?usp=sharing

### **Use Case 1: Probability Estimation Using the Law of Large Numbers in Credit Risk Assessment**

#### **Concept & Purpose**
The **Law of Large Numbers** states that as the number of independent trials increases, the observed relative frequency of an event converges to its true probability. This principle allows for stable probability estimates from empirical data.

- **Purpose**: To estimate default probabilities in a loan portfolio.
- **Assumptions**:
  - Trials (loans) are independent.
  - The underlying probability of default is constant.
  - A sufficiently large sample is available.

#### **Application in Finance**
A bank wants to estimate the probability of default (PD) for small business loans. Using historical data from 10,000 loans, they compute the cumulative default rate as more loans are observed.

#### **Structured Data Example**
| Loans Observed (n) | Defaults Count | Cumulative Default Rate |
|--------------------|----------------|-------------------------|
| 100                | 5              | 5.00%                   |
| 1,000              | 48             | 4.80%                   |
| 5,000              | 245            | 4.90%                   |
| 10,000             | 490            | 4.90%                   |

#### **Visualization**
```plaintext
Cumulative Default Rate (%)
           ^
           |
        5.0|    ••••••••••••••••••••••••••••••••••→ converges to ~4.9%
           |    •
           |    •
        4.9|    •
           |    •
           |    •
           +------------------------------------>
                100   1k     5k     10k   Loans Observed
```
- **Interpretation**: The default rate stabilizes around 4.9% as more loans are included, demonstrating the Law of Large Numbers.

#### **Key Insights & Decision Implications**
- **Insight**: With sufficient data, PD estimates become reliable for pricing and provisioning.
- **Decision**: Set aside capital reserves based on the converged PD. Use smaller samples cautiously due to higher variability.

---

### **Use Case 2: Decision Tree Analysis for Product Launch Strategy**

#### **Concept & Purpose**
A **tree diagram** visually maps sequential decisions and chance events, enabling calculation of joint probabilities for different outcomes.

- **Purpose**: To evaluate the probability of success for a new product launch considering market acceptance and competitor response.
- **Assumptions**:
  - Events are independent (e.g., market reaction independent of prior internal decisions).
  - Probabilities at each node are known or estimated.

#### **Application in Business**
A company considers launching a product. Key stages:
1. Market research outcome (Positive/Negative)
2. Competitor reaction (Launch rival product/Ignore)

#### **Tree Diagram & Probability Table**
```
Stage 1: Market Research  
P(Positive) = 0.7 → Stage 2: Competitor Reaction  
                    P(Launch) = 0.4 → Outcome: Success with competition (0.28)
                    P(Ignore) = 0.6 → Outcome: Success without competition (0.42)  
P(Negative) = 0.3 → Stage 2: Competitor Reaction  
                    P(Launch) = 0.8 → Outcome: Failure with competition (0.24)
                    P(Ignore) = 0.2 → Outcome: Failure without competition (0.06)
```

#### **Visualization**
```plaintext
Probability Distribution of Outcomes
Success w/ competition: 28%
Success w/o competition: 42%
Failure w/ competition: 24%
Failure w/o competition: 6%
```
- **Interpretation**: Most likely outcome is “Success without competition” (42%). Competitor reaction significantly impacts success.

#### **Key Insights & Decision Implications**
- **Insight**: Even with positive research, competitor launch reduces success probability.
- **Decision**: Invest in pre-emptive marketing if competitor reaction is likely. Consider contingency plans for competitive response.

---

### **Use Case 3: Set Theory for Operational Risk Event Classification**

#### **Concept & Purpose**
**Mutually exclusive (disjoint)** and **collectively exhaustive** sets help categorize risk events without overlap, ensuring comprehensive coverage.

- **Purpose**: To classify operational risk incidents in a manufacturing firm.
- **Assumptions**:
  - Each incident belongs to exactly one category.
  - Categories cover all possible incidents.

#### **Application in Risk Management**
A company categorizes incidents as:
- A: Equipment failure
- B: Human error
- C: Supply chain disruption  
These are mutually exclusive and collectively exhaustive.

#### **Incident Count Table**
| Category       | Number of Incidents | Probability |
|----------------|---------------------|-------------|
| Equipment      | 120                 | 0.40        |
| Human Error    | 90                  | 0.30        |
| Supply Chain   | 90                  | 0.30        |
| **Total**      | **300**             | **1.00**    |

#### **Visualization**
```plaintext
Venn Diagram (simplified): Three non-overlapping circles in a rectangle (sample space).
```
- **Interpretation**: No incident belongs to two categories. Probabilities sum to 1, confirming exhaustiveness.

#### **Key Insights & Decision Implications**
- **Insight**: Equipment failure is the most frequent risk.
- **Decision**: Prioritize preventive maintenance and training for equipment handling. Allocate resources proportionally to incident probabilities.

---

### **Use Case 4: Joint & Marginal Probabilities in Customer Segmentation**

#### **Concept & Purpose**
**Joint probabilities** describe the likelihood of two events occurring together (e.g., customer demographics and behavior). **Marginal probabilities** describe probabilities for single variables.

- **Purpose**: To segment customers by age group and purchase frequency for targeted marketing.
- **Assumptions**:
  - Data comes from a random sample.
  - Variables are discrete and categorizable.

#### **Application in Marketing**
A retail chain analyzes 1,000 customers:

#### **Contingency Table (Counts & Probabilities)**
|            | Age < 30 | Age 30–50 | Age > 50 | **Marginal (Purchase)** |
|------------|----------|-----------|----------|-------------------------|
| Frequent   | 100      | 150       | 50       | 300 (0.30)              |
| Occasional | 150      | 200       | 100      | 450 (0.45)              |
| Rare       | 50       | 100       | 100      | 250 (0.25)              |
| **Marginal (Age)** | 300 (0.30) | 450 (0.45) | 250 (0.25) | **1000 (1.00)** |

Joint probabilities are cell counts divided by 1000 (e.g., P(Age<30 & Frequent) = 0.10).

#### **Visualization**
```plaintext
Stacked Bar Chart: 
X-axis: Age groups  
Y-axis: Proportion of customers  
Bars split by purchase frequency (Frequent/Occasional/Rare).
```
- **Interpretation**: Customers aged 30–50 are the largest segment and most likely to purchase frequently.

#### **Key Insights & Decision Implications**
- **Insight**: Purchase frequency varies by age; younger customers are less frequent buyers.
- **Decision**: Target age 30–50 with loyalty programs. For younger customers, focus on activation campaigns.

---

### **Use Case 5: Conditional Probability & Bayes’ Theorem in Medical Diagnostics**

#### **Concept & Purpose**
**Conditional probability** quantifies the likelihood of an event given another has occurred. **Bayes’ Theorem** updates prior beliefs with new evidence.

- **Purpose**: To determine the probability of a disease given a positive test result.
- **Assumptions**:
  - Test sensitivity and specificity are known.
  - Prior disease prevalence is known.

#### **Application in Healthcare**
A disease affects 1% of a population. Test sensitivity = 95%, specificity = 90%.

#### **Probability Calculations**
- Prior: P(Disease) = 0.01  
- P(Positive|Disease) = 0.95  
- P(Positive|No Disease) = 0.10  

Using Bayes:
\[
P(Disease|Positive) = \frac{0.95 \times 0.01}{0.95 \times 0.01 + 0.10 \times 0.99} \approx 0.087
\]

#### **Visualization**
```plaintext
Before Test: Prior Probability = 1%
After Positive Test: Posterior Probability = 8.7%
```
- **Interpretation**: Even with a positive test, the actual probability of having the disease is only 8.7% due to low prevalence and false positives.

#### **Key Insights & Decision Implications**
- **Insight**: Low-prevalence diseases yield many false positives even with accurate tests.
- **Decision**: Use confirmatory testing after initial positive results. Communicate risks carefully to avoid unnecessary alarm.

---

### **Use Case 6: Independence Testing in A/B Marketing Campaigns**

#### **Concept & Purpose**
Two events are **independent** if knowing one does not change the probability of the other. In A/B testing, we check if campaign version and conversion are independent.

- **Purpose**: To determine if a new website design (Version B) leads to higher conversion rates than the old design (Version A).
- **Assumptions**:
  - Users are randomly assigned to versions.
  - Conversions are independent across users.

#### **Application in Digital Marketing**
Two versions tested on 2,000 users:

#### **Contingency Table**
| Version | Converted | Not Converted | Total   |
|---------|-----------|---------------|---------|
| A       | 120       | 880           | 1,000   |
| B       | 180       | 820           | 1,000   |
| **Total** | **300**   | **1,700**     | **2,000** |

#### **Chi-Square Test for Independence**
- Expected frequencies calculated under independence.
- Chi-square statistic = 10.59, p-value < 0.01 → Reject independence.

#### **Visualization**
```plaintext
Bar Chart: 
X-axis: Version A vs B  
Y-axis: Conversion rate (%)  
Version A: 12%, Version B: 18%
```
- **Interpretation**: Conversion rates differ significantly; Version B performs better.

#### **Key Insights & Decision Implications**
- **Insight**: Design B increases conversions by 6 percentage points.
- **Decision**: Roll out Version B to all users. Monitor long-term effects on customer behavior.

---

If you would like a consolidated PDF version of these use cases with refined tables and visualizations, I can prepare that for you. Would you also like to explore specific applications in your industry?
