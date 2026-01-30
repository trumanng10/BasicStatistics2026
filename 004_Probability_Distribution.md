# **Six Statistical Use Cases Based on Probability Distributions (Documents 401–408)**

---

## **Use Case 1: Customer Arrival Modeling Using Probability Distributions**

### **Concept & Purpose**
- **Statistical Concept**: Discrete vs. continuous random variables, probability mass function (PMF) vs. probability density function (PDF).
- **Purpose**: Model customer arrivals per hour at a service center to optimize staffing.
- **Assumptions**:
  - Arrivals are independent.
  - Arrival rate is constant over time (Poisson process implied).
  - Data follows a known probability distribution (Poisson for counts, exponential for inter-arrival times).

### **Application in Business**
A call center wants to predict the number of incoming calls per hour to schedule agents efficiently. Historical data shows an average of 10 calls per hour.

### **Structured Data & Probability Table**

**Discrete Distribution (Poisson PMF)** for number of calls per hour (λ = 10):

| Calls per Hour (x) | Probability P(X = x) |
|--------------------|----------------------|
| 0                  | 0.000045             |
| 5                  | 0.037833             |
| 10                 | 0.125110             |
| 15                 | 0.034718             |
| 20                 | 0.001866             |

**Continuous Distribution (Exponential PDF)** for time between calls (rate = 10 calls/hour):

| Inter-arrival Time (minutes) | Probability Density |
|------------------------------|---------------------|
| 0                            | 0.1667              |
| 5                            | 0.0820              |
| 10                           | 0.0403              |
| 15                           | 0.0198              |

### **Visualization**
```plaintext
Left: Bar chart of Poisson PMF (x: calls/hour, y: probability)
Right: Line chart of Exponential PDF (x: minutes between calls, y: density)
```
- **Interpretation**: The Poisson PMF shows the likelihood of different call volumes. The exponential PDF shows that shorter inter-arrival times are more likely.

### **Key Insights & Decision Implications**
- **Insight**: Most hours have 8–12 calls; very few have >20 calls.
- **Decision**: Staff 2–3 agents during peak hours, use a smaller team during low-volume periods. Implement an interactive dashboard to simulate different arrival rates and staffing levels.

---

## **Use Case 2: Cumulative Probability for Service Level Agreement (SLA) Compliance**

### **Concept & Purpose**
- **Statistical Concept**: Cumulative distribution function (CDF), quantiles.
- **Purpose**: Determine the probability that service response time meets SLA thresholds.
- **Assumptions**:
  - Response times are independent and identically distributed.
  - The distribution of response times is known (e.g., log-normal).

### **Application in IT Services**
An IT support team tracks ticket resolution times. The SLA requires 90% of tickets to be resolved within 4 hours.

### **Cumulative Probability Table**
Response times (in hours) follow a log-normal distribution with mean = 2.5, sd = 1.2.

| Time (hours) | Cumulative Probability |
|--------------|------------------------|
| 1            | 0.10                   |
| 2            | 0.45                   |
| 3            | 0.70                   |
| 4            | 0.85                   |
| 5            | 0.94                   |

### **Visualization**
```plaintext
CDF Plot: 
X-axis: Response time (hours)
Y-axis: Cumulative probability
Line shows increasing curve; dashed lines at 4 hours (SLA threshold) and 0.9 probability.
```
- **Interpretation**: Only 85% of tickets are resolved within 4 hours, missing the 90% SLA.

### **Key Insights & Decision Implications**
- **Insight**: Current performance is below SLA; the 90th percentile is at ~4.8 hours.
- **Decision**: Invest in additional support staff or process automation. Create a real-time dashboard that monitors cumulative compliance and alerts when performance drops below thresholds.

---

## **Use Case 3: Expected Value and Variance in Project Risk Analysis**

### **Concept & Purpose**
- **Statistical Concept**: Expected value (mean) and variance of random variables, linear transformations.
- **Purpose**: Evaluate the expected cost and risk (variability) of a project with multiple uncertain components.
- **Assumptions**:
  - Cost components are independent.
  - Distributions of individual costs are known.

### **Application in Project Management**
A construction project has three uncertain cost elements: materials, labor, and permits.

### **Cost Distribution Table**

| Cost Component   | Expected Value (μ) | Variance (σ²) |
|------------------|--------------------|---------------|
| Materials        | $50,000            | 4,000,000     |
| Labor            | $30,000            | 2,250,000     |
| Permits          | $10,000            | 250,000       |

**Total Expected Cost**:  
\[
E[Total] = 50,000 + 30,000 + 10,000 = \$90,000
\]

**Total Variance (assuming independence)**:  
\[
Var(Total) = 4,000,000 + 2,250,000 + 250,000 = 6,500,000
\]  
Standard deviation = \(\sqrt{6,500,000} \approx \$2,550\)

### **Visualization**
```plaintext
Tornado Diagram:
X-axis: Cost impact ($)
Bars for each component showing mean ± 1 standard deviation.
```
- **Interpretation**: Materials cost has the highest uncertainty; labor is moderately variable; permits are relatively stable.

### **Key Insights & Decision Implications**
- **Insight**: Total project cost is expected to be $90,000 but could range from $84,900 to $95,100 (≈ μ ± 2σ) with 95% probability.
- **Decision**: Allocate contingency budget based on variance (e.g., 10% contingency). Use a Monte Carlo simulation dashboard to model different scenarios and assess overall risk exposure.

---

## **Use Case 4: Normal Distribution in Quality Control (Six Sigma)**

### **Concept & Purpose**
- **Statistical Concept**: Normal distribution, 1-2-3 sigma rules, probability density function.
- **Purpose**: Monitor manufacturing process quality and detect deviations.
- **Assumptions**:
  - Process output is normally distributed.
  - Measurements are independent.
  - Process is in control (mean and variance stable).

### **Application in Manufacturing**
A factory produces bolts with target length = 100 mm, standard deviation = 2 mm. Specification limits: 96 mm to 104 mm.

### **Probability Calculations Using Sigma Rules**

| Interval (mm)        | Sigma Distance | Probability Inside |
|----------------------|----------------|--------------------|
| 98 to 102 (μ ± 1σ)   | 1σ             | 68.3%              |
| 96 to 104 (μ ± 2σ)   | 2σ             | 95.4%              |
| 94 to 106 (μ ± 3σ)   | 3σ             | 99.7%              |

### **Visualization**
```plaintext
Bell Curve (Normal Distribution):
X-axis: Bolt length (mm)
Y-axis: Probability density
Vertical lines at 96, 100, 104.
Shaded area between 96 and 104 = 95.4%.
```
- **Interpretation**: About 4.6% of bolts are expected to be out of spec (defect rate).

### **Key Insights & Decision Implications**
- **Insight**: Current process capability (Cp) = (104-96)/(6*2) = 0.67 < 1, indicating poor capability.
- **Decision**: Implement process improvements to reduce variation. Use control charts (dashboard) to monitor mean and variability in real time, with alerts when points fall outside 3σ limits.

---

## **Use Case 5: Z-scores for Standardized Employee Performance Evaluation**

### **Concept & Purpose**
- **Statistical Concept**: Z-scores, standard normal distribution, percentile ranks.
- **Purpose**: Compare employee performance across different departments or roles on a common scale.
- **Assumptions**:
  - Performance scores are normally distributed (or can be transformed).
  - Mean and standard deviation are known or estimated reliably.

### **Application in HR**
A company wants to identify top performers across sales (mean = 80, sd = 10) and engineering (mean = 70, sd = 15) teams.

### **Z-score Calculation Table**

| Employee | Department  | Raw Score | Z-score | Percentile |
|----------|-------------|-----------|---------|------------|
| A        | Sales       | 95        | 1.5     | 93.3%      |
| B        | Sales       | 80        | 0.0     | 50.0%      |
| C        | Engineering | 85        | 1.0     | 84.1%      |
| D        | Engineering | 70        | 0.0     | 50.0%      |

### **Visualization**
```plaintext
Standard Normal Curve (Z-distribution):
X-axis: Z-score
Y-axis: Density
Points plotted at Z-scores of employees; shaded areas show percentiles.
```
- **Interpretation**: Employee A is 1.5 standard deviations above the sales mean, outperforming 93.3% of sales peers.

### **Key Insights & Decision Implications**
- **Insight**: Z-scores allow fair cross-departmental comparison. Top performers can be identified regardless of team-specific scoring.
- **Decision**: Use Z-scores in performance dashboards to rank employees, allocate bonuses, and identify candidates for promotion. Set thresholds (e.g., Z > 1.5) for high-potential programs.

---

## **Use Case 6: Binomial Distribution for Marketing Campaign Response Analysis**

### **Concept & Purpose**
- **Statistical Concept**: Binomial distribution, probability of successes in n trials.
- **Purpose**: Predict the number of positive responses (e.g., conversions) from a marketing campaign.
- **Assumptions**:
  - Each contact is an independent trial.
  - Probability of success (conversion) is constant for each contact.
  - Number of trials (contacts) is fixed.

### **Application in Digital Marketing**
An email campaign is sent to 1,000 subscribers. Historical conversion rate (click-through) is 5%.

### **Binomial Probability Table**

| Conversions (x) | Probability P(X = x) | Cumulative Probability |
|-----------------|----------------------|------------------------|
| 40              | 0.0176               | 0.150                  |
| 50              | 0.0368               | 0.540                  |
| 60              | 0.0220               | 0.880                  |
| 70              | 0.0067               | 0.980                  |

### **Visualization**
```plaintext
Binomial PMF Bar Chart:
X-axis: Number of conversions (0–100)
Y-axis: Probability
Bars centered near 50 (expected value = np = 50).
```
- **Interpretation**: The most likely outcome is 50 conversions, but there is a 95% chance (approximate) that conversions will be between 37 and 63 (using normal approximation).

### **Key Insights & Decision Implications**
- **Insight**: Campaign performance is predictable; deviations beyond ±2σ (≈ 40–60 conversions) may indicate issues.
- **Decision**: Set up an A/B testing dashboard that compares observed vs. expected conversions using binomial confidence intervals. If actual conversions fall below the lower bound, pause the campaign and investigate.

---

## **Summary**
These six use cases demonstrate how probability distributions and related concepts are applied in real-world business, finance, and research contexts. Each case includes:
- Clear statistical explanations,
- Practical applications,
- Structured tables and visualizations,
- Actionable insights and decision frameworks.
