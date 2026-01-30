# **Six Statistical Use Cases Based on Sampling Distributions (Documents 5.01–5.07)**

###Graph:
https://colab.research.google.com/drive/10SGUImOZGd2kfZW_ldYbnRPIqcG54cst?usp=sharing
###
---

## **Use Case 1: Estimating Population Mean for Customer Lifetime Value (CLV)**

### **Concept & Purpose**
- **Statistical Concept**: Sampling distribution of the sample mean, Central Limit Theorem (CLT), standard error.
- **Purpose**: Estimate the average CLV of all customers based on a sample, and quantify the uncertainty of the estimate.
- **Assumptions**:
  - The sample is a simple random sample from the population.
  - The sample size is large enough (n ≥ 30) for CLT to apply, or the population is normally distributed.
  - Observations are independent.

### **Application in Business**
A retail company wants to estimate the average CLV of its 500,000 customers. It draws a random sample of 200 customers and calculates their CLV. The sample mean is $1,200 with a standard deviation of $400.

### **Structured Data & Calculations**
- Population size: N = 500,000
- Sample size: n = 200
- Sample mean: \(\bar{x} = \$1,200\)
- Sample standard deviation: s = $400
- Estimated standard error: \(\sigma_{\bar{x}} \approx \frac{s}{\sqrt{n}} = \frac{400}{\sqrt{200}} \approx \$28.28\)

**Probability Table for Sample Means (based on CLT):**
| Interval Around Population Mean | Z-score | Probability |
|---------------------------------|---------|-------------|
| \(\mu \pm 1 \sigma_{\bar{x}}\)  | ±1      | 68.3%       |
| \(\mu \pm 1.96 \sigma_{\bar{x}}\) | ±1.96   | 95.0%       |
| \(\mu \pm 2.58 \sigma_{\bar{x}}\) | ±2.58   | 99.0%       |

### **Visualization**
```plaintext
Sampling Distribution of Sample Mean (Bell Curve)
X-axis: Sample mean CLV ($)
Y-axis: Probability density
Vertical line at sample mean $1,200; shaded area for 95% CI: $1,200 ± 1.96*28.28 = [$1,144.6, $1,255.4]
```
- **Interpretation**: The sampling distribution is approximately normal. The 95% confidence interval suggests that the true population mean CLV lies between $1,144.6 and $1,255.4 with 95% confidence.

### **Key Insights & Decision Implications**
- **Insight**: The estimate has a margin of error of about ±$55.4 (at 95% confidence). Larger samples would reduce this margin.
- **Decision**: Use the confidence interval for budget planning and customer segmentation. Implement an interactive dashboard that updates the CI as new sample data arrives, allowing dynamic adjustment of marketing strategies.

---

## **Use Case 2: Designing a Representative Political Poll**

### **Concept & Purpose**
- **Statistical Concept**: Simple random sampling, stratified random sampling, sampling bias, nonresponse bias.
- **Purpose**: Obtain a sample that accurately represents the voting population to predict election outcomes.
- **Assumptions**:
  - A complete sampling frame is available (e.g., voter registration list).
  - Respondents answer truthfully.
  - Nonresponse is random or accounted for.

### **Application in Research**
A polling agency wants to predict the outcome of a mayoral election in a city with 1 million eligible voters. They plan to survey 1,000 voters.

### **Sampling Design Table**
| Sampling Method          | Description                                   | Advantage                                  | Disadvantage                               |
|--------------------------|-----------------------------------------------|--------------------------------------------|--------------------------------------------|
| Simple Random            | Randomly select 1,000 from voter list         | Unbiased, simple                           | Requires complete list, may be costly      |
| Stratified Random        | Divide by age group, sample proportionally    | Ensures representation of key demographics | Need demographic data, more complex        |
| Cluster Sampling         | Randomly select neighborhoods, survey all     | Cost-effective for face-to-face            | Higher sampling error if clusters are similar |

**Potential Biases and Mitigation:**
| Bias Type         | Risk                                          | Mitigation                                  |
|-------------------|-----------------------------------------------|---------------------------------------------|
| Undercoverage     | Unregistered voters not in frame              | Use multiple frames (e.g., phone + online)  |
| Nonresponse       | Young voters less likely to respond           | Weighting, follow-ups                       |
| Response          | Social desirability (e.g., shy Trump voters)  | Anonymous surveys, neutral wording          |

### **Visualization**
```plaintext
Bar Chart: Sample vs. Population Demographics
X-axis: Age groups (18-30, 31-50, 51+)
Y-axis: Percentage
Two bars per group: population % and sample %.
Goal: bars should align closely.
```
- **Interpretation**: If the sample proportions match population proportions, the sample is representative. Discrepancies indicate potential coverage or nonresponse bias.

### **Key Insights & Decision Implications**
- **Insight**: Stratified sampling ensures demographic representation but adds complexity. Nonresponse bias can skew results.
- **Decision**: Use stratified random sampling with oversampling of underrepresented groups. Develop a polling dashboard that tracks response rates by demographic and applies real-time weighting adjustments.

---

## **Use Case 3: Monitoring Defect Rates in Manufacturing**

### **Concept & Purpose**
- **Statistical Concept**: Sampling distribution of the sample proportion, normal approximation conditions.
- **Purpose**: Estimate the proportion of defective items in a production batch and set up control limits.
- **Assumptions**:
  - The sample is random.
  - The sample size is large enough: \(n\hat{p} \geq 15\) and \(n(1-\hat{p}) \geq 15\).
  - Items are independent.

### **Application in Quality Control**
A factory produces 10,000 electronic components per day. Quality control inspects a random sample of 500 items each day. The historical defect rate is 2%.

### **Probability Calculations**
- Population proportion: \(\pi = 0.02\)
- Sample size: n = 500
- Standard error: \(\sigma_p = \sqrt{\frac{\pi(1-\pi)}{n}} = \sqrt{\frac{0.02*0.98}{500}} \approx 0.00626\)
- Control limits (95%): \(0.02 \pm 1.96*0.00626 = [0.0077, 0.0323]\)

**Sampling Distribution of Sample Proportion (Table):**
| Sample Defect Rate (p) | Probability (approx) | Cumulative Probability |
|------------------------|----------------------|------------------------|
| p < 0.01               | 5%                   | 5%                     |
| 0.01 ≤ p < 0.02        | 45%                  | 50%                    |
| 0.02 ≤ p < 0.03        | 45%                  | 95%                    |
| p ≥ 0.03               | 5%                   | 100%                   |

### **Visualization**
```plaintext
Control Chart for Sample Proportion
X-axis: Day
Y-axis: Defect rate
Horizontal lines: mean (0.02), upper control limit (0.0323), lower control limit (0.0077).
Points: daily defect rates.
```
- **Interpretation**: Points within control limits indicate stable process. A point above UCL signals a potential increase in defect rate, triggering investigation.

### **Key Insights & Decision Implications**
- **Insight**: The sampling distribution allows us to distinguish common cause variation from special cause variation.
- **Decision**: Implement a real-time quality dashboard that plots daily defect rates against control limits. Automate alerts when limits are breached, and link to root-cause analysis workflows.

---

## **Use Case 4: Financial Risk Assessment for Loan Portfolios**

### **Concept & Purpose**
- **Statistical Concept**: Three distributions (population, sample, sampling distribution), z-scores, probability of extreme sample means.
- **Purpose**: Assess the risk that the average return on a loan portfolio falls below a threshold.
- **Assumptions**:
  - Portfolio returns are normally distributed (or CLT applies for sample means).
  - Historical mean and standard deviation are known.

### **Application in Finance**
A bank holds a portfolio of 1,000 small business loans. The average annual return (population mean) is 8% with a standard deviation of 5%. The risk team wants to know the probability that a random sample of 100 loans has an average return below 5%.

### **Calculations**
- Population mean: \(\mu = 0.08\)
- Population standard deviation: \(\sigma = 0.05\)
- Sample size: n = 100
- Standard error: \(\sigma_{\bar{x}} = \frac{0.05}{\sqrt{100}} = 0.005\)
- Z-score for sample mean 0.05: \(z = \frac{0.05 - 0.08}{0.005} = -6\)
- Probability: P(\(\bar{x} < 0.05\)) ≈ 0 (from z-table)

**Probability Table for Sample Mean Returns:**
| Sample Mean Return | Z-score | Probability (Cumulative) |
|--------------------|---------|--------------------------|
| 0.06               | -4      | 0.00003                  |
| 0.07               | -2      | 0.0228                   |
| 0.08               | 0       | 0.5                      |
| 0.09               | 2       | 0.9772                   |
| 0.10               | 4       | 0.99997                  |

### **Visualization**
```plaintext
Three Distributions Overlay:
1. Population distribution: normal, mean 0.08, sd 0.05 (wide).
2. Sample distribution (one sample): histogram of 100 loans.
3. Sampling distribution: normal, mean 0.08, sd 0.005 (narrow).
Vertical line at 0.05.
```
- **Interpretation**: The sampling distribution is much narrower than the population distribution. The probability of a sample mean below 5% is virtually zero, indicating low risk for large samples.

### **Key Insights & Decision Implications**
- **Insight**: Even though individual loans are risky (sd=5%), the average return of a large sample is very stable. Diversification reduces risk.
- **Decision**: Use sampling distribution concepts to set risk limits for portfolio segments. Create a dashboard that simulates sample mean distributions for different portfolio sizes and highlights probabilities of breaching thresholds.

---

## **Use Case 5: Determining Sample Size for Employee Satisfaction Survey**

### **Concept & Purpose**
- **Statistical Concept**: Margin of error, standard error, sample size formula for means and proportions.
- **Purpose**: Determine the minimum sample size required to estimate employee satisfaction within a specified margin of error.
- **Assumptions**:
  - The population is large (e.g., >10,000).
  - The variable of interest is approximately normally distributed.
  - A desired confidence level (e.g., 95%) and margin of error are chosen.

### **Application in HR**
A company with 20,000 employees wants to conduct a satisfaction survey. The satisfaction score is on a 1-10 scale. Previous surveys show a standard deviation of 2.5. They want a margin of error of ±0.3 points with 95% confidence.

### **Sample Size Calculation**
- Confidence level: 95% → z* = 1.96
- Margin of error (E): 0.3
- Estimated standard deviation (σ): 2.5
- Formula: \(n = \left(\frac{z^* \sigma}{E}\right)^2 = \left(\frac{1.96 * 2.5}{0.3}\right)^2 \approx 266.8\) → round up to 267.

**Sample Size Table for Different Scenarios:**
| Margin of Error (E) | Confidence Level | Required Sample Size (n) |
|---------------------|------------------|--------------------------|
| 0.5                 | 95%              | 96                       |
| 0.3                 | 95%              | 267                      |
| 0.2                 | 95%              | 600                      |
| 0.3                 | 99%              | 462                      |

### **Visualization**
```plaintext
Line Chart: Sample Size vs. Margin of Error
X-axis: Margin of Error (from 0.1 to 1)
Y-axis: Required Sample Size
Multiple lines for different confidence levels (90%, 95%, 99%).
```
- **Interpretation**: As the desired margin of error decreases, the required sample size increases sharply. Higher confidence also requires larger samples.

### **Key Insights & Decision Implications**
- **Insight**: A sample of 267 employees is sufficient to estimate the overall satisfaction within ±0.3 points. Stratification may reduce required size if subgroups are of interest.
- **Decision**: Use an interactive sample size calculator in the survey planning dashboard. Input parameters (population size, confidence level, margin of error, estimated variability) to get recommended sample sizes and associated costs.

---

## **Use Case 6: Analyzing A/B Test Results for Website Conversion**

### **Concept & Purpose**
- **Statistical Concept**: Sampling distribution of the difference between two proportions, hypothesis testing.
- **Purpose**: Determine if a new website design (B) leads to a higher conversion rate than the old design (A).
- **Assumptions**:
  - Visitors are randomly assigned to A or B.
  - Observations are independent.
  - Sample sizes are large enough for normal approximation.

### **Application in Digital Marketing**
An e-commerce site tests two designs: A (control) and B (new). Out of 10,000 visitors, 5,000 see each. Conversion counts: A: 400 conversions, B: 480 conversions.

### **Data and Calculations**
- Proportion A: \(\hat{p}_A = 400/5000 = 0.08\)
- Proportion B: \(\hat{p}_B = 480/5000 = 0.096\)
- Difference: \(\hat{p}_B - \hat{p}_A = 0.016\)
- Pooled proportion: \(\hat{p} = (400+480)/(5000+5000) = 0.088\)
- Standard error of difference: \(\sqrt{\hat{p}(1-\hat{p})(\frac{1}{n_A}+\frac{1}{n_B})} = \sqrt{0.088*0.912*(1/5000+1/5000)} \approx 0.00567\)
- Z-score: \(z = 0.016 / 0.00567 \approx 2.82\)
- p-value: P(Z > 2.82) ≈ 0.0024 (one-tailed)

**Probability Table for Differences under Null Hypothesis:**
| Difference (B - A) | Z-score | Probability (Cumulative) |
|--------------------|---------|--------------------------|
| -0.01              | -1.76   | 0.0392                   |
| 0.00               | 0.00    | 0.5000                   |
| 0.01               | 1.76    | 0.9608                   |
| 0.016              | 2.82    | 0.9976                   |

### **Visualization**
```plaintext
Sampling Distribution of Difference under Null Hypothesis (Normal, mean=0, se=0.00567)
X-axis: Difference in conversion rates (B - A)
Y-axis: Probability density
Vertical line at observed difference (0.016); shaded area for p-value (right tail).
```
- **Interpretation**: The observed difference is far in the right tail of the null distribution, indicating statistical significance.

### **Key Insights & Decision Implications**
- **Insight**: The new design increases conversion by 1.6 percentage points (a 20% relative improvement), and the result is statistically significant (p < 0.01).
- **Decision**: Roll out design B to all visitors. Implement an A/B testing dashboard that automatically calculates significance, confidence intervals, and lifts for multiple metrics, with alerts when tests reach significance.

---

## **Summary**
These six use cases demonstrate how sampling distribution concepts are applied in business, finance, and research. Each case includes:
- Clear statistical explanations and assumptions.
- Practical applications with realistic scenarios.
- Structured tables and visualizations.
- Key insights and actionable decision frameworks.

By leveraging these concepts, organizations can make data-driven decisions, optimize processes, and manage risks effectively. Interactive dashboards and probability tables enhance real-time decision-making and strategic planning.

If you need detailed **Excel templates**, **R/Python code**, or **dashboard wireframes** for any of these use cases, please let me know.
