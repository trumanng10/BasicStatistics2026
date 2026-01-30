# **Six Statistical Use Cases Based on Confidence Intervals (Documents 6.01–6.07)**

---
## Graph:
https://colab.research.google.com/drive/1b18fZPvCqDAKeuhf-dVX0pIbl23_9Gux?usp=sharing

## **Use Case 1: Estimating Average Customer Spend with Known Population Standard Deviation**

### **Concept & Purpose**
- **Statistical Concept**: Confidence interval for a population mean when the population standard deviation (σ) is known, using the z-distribution.
- **Purpose**: Estimate the average transaction value (mean spend) of all customers in a retail chain with a known historical standard deviation.
- **Assumptions**:
  - The sample is a simple random sample.
  - The population standard deviation is known and constant.
  - The sampling distribution of the sample mean is approximately normal (by CLT if n ≥ 30, or population is normally distributed).

### **Application in Retail**
A national retail chain wants to estimate the average transaction value (ATV) of its 2 million customers. Historical data shows the population standard deviation is $50. A random sample of 100 transactions yields a sample mean of $85.

### **Structured Data & Calculations**
- Population standard deviation (σ): $50
- Sample size (n): 100
- Sample mean (\(\bar{x}\)): $85
- Confidence level: 95% → z* = 1.96

**Standard error (SE)**:  
\[
SE = \frac{\sigma}{\sqrt{n}} = \frac{50}{\sqrt{100}} = 5
\]

**Margin of error (ME)**:  
\[
ME = z^* \times SE = 1.96 \times 5 = 9.8
\]

**95% Confidence Interval**:  
\[
\bar{x} \pm ME = 85 \pm 9.8 = [75.2, 94.8]
\]

**Probability Table for Sample Means (under normality)**:
| Interval (around μ) | Z-score | Probability |
|---------------------|---------|-------------|
| μ ± 1.645 SE        | ±1.645  | 90%         |
| μ ± 1.96 SE         | ±1.96   | 95%         |
| μ ± 2.576 SE        | ±2.576  | 99%         |

### **Visualization**
```plaintext
Normal Distribution (Bell Curve):
X-axis: Sample mean transaction value ($)
Y-axis: Probability density
Vertical line at sample mean $85; shaded area between $75.2 and $94.8 represents 95% CI.
```
- **Interpretation**: We are 95% confident that the true population mean transaction value lies between $75.2 and $94.8. The margin of error is ±$9.8.

### **Key Insights & Decision Implications**
- **Insight**: The ATV estimate is relatively precise due to the large sample and known σ. The CI helps in revenue forecasting and inventory planning.
- **Decision**: Use this CI to set realistic sales targets. Implement an interactive dashboard where managers can adjust confidence levels (90%, 95%, 99%) and see how the CI changes, aiding in risk-aware decision-making.

---

## **Use Case 2: Quality Control – Estimating Defect Proportion in Manufacturing**

### **Concept & Purpose**
- **Statistical Concept**: Confidence interval for a population proportion, using the normal approximation.
- **Purpose**: Estimate the proportion of defective items in a production batch to ensure quality standards.
- **Assumptions**:
  - The sample is random.
  - The sample size is large enough: \(n\hat{p} \geq 15\) and \(n(1-\hat{p}) \geq 15\).
  - The normal approximation is valid.

### **Application in Manufacturing**
A factory produces 50,000 units of a component monthly. A random sample of 400 units is inspected, and 12 are found defective.

### **Structured Data & Calculations**
- Sample size (n): 400
- Number of defects (x): 12
- Sample proportion (\(\hat{p}\)): \(12/400 = 0.03\)
- Confidence level: 95% → z* = 1.96

**Standard error (SE)**:  
\[
SE = \sqrt{\frac{\hat{p}(1-\hat{p})}{n}} = \sqrt{\frac{0.03 \times 0.97}{400}} \approx 0.0085
\]

**Margin of error (ME)**:  
\[
ME = z^* \times SE = 1.96 \times 0.0085 \approx 0.0167
\]

**95% Confidence Interval**:  
\[
\hat{p} \pm ME = 0.03 \pm 0.0167 = [0.0133, 0.0467]
\]

**Probability Table for Sample Proportions**:
| Sample Proportion (p) | Z-score | Cumulative Probability |
|-----------------------|---------|------------------------|
| 0.02                  | -1.18   | 0.1190                 |
| 0.03                  | 0.00    | 0.5000                 |
| 0.04                  | 1.18    | 0.8810                 |

### **Visualization**
```plaintext
Normal Approximation to Binomial Distribution:
X-axis: Defect proportion (0 to 0.07)
Y-axis: Probability density
Vertical line at sample proportion 0.03; shaded area between 0.0133 and 0.0467 represents 95% CI.
```
- **Interpretation**: We are 95% confident that the true defect proportion in the population is between 1.33% and 4.67%. The estimate has a margin of error of ±1.67 percentage points.

### **Key Insights & Decision Implications**
- **Insight**: The defect rate is likely below the 5% threshold, but the upper bound of 4.67% is close, warranting monitoring.
- **Decision**: Implement a real-time quality dashboard that plots daily defect proportions with CIs. Set up alerts when the CI upper bound exceeds 5%, triggering root-cause analysis.

---

## **Use Case 3: Sample Size Determination for Employee Satisfaction Survey**

### **Concept & Purpose**
- **Statistical Concept**: Sample size calculation for estimating a mean or proportion with a desired margin of error and confidence level.
- **Purpose**: Determine the minimum sample size required to estimate overall employee satisfaction within a specified precision.
- **Assumptions**:
  - The population is large (e.g., >10,000).
  - For means: an estimate of population standard deviation is available.
  - For proportions: an estimate of the proportion (or the conservative 0.5) is used.

### **Application in HR**
A company with 10,000 employees wants to conduct a satisfaction survey (scale 1–10). Previous surveys show a standard deviation of 2.0. They desire a margin of error of ±0.3 points with 95% confidence.

### **Sample Size Calculation for Mean**
- Confidence level: 95% → z* = 1.96
- Margin of error (ME): 0.3
- Estimated standard deviation (σ): 2.0

**Formula**:  
\[
n = \left( \frac{z^* \times \sigma}{ME} \right)^2 = \left( \frac{1.96 \times 2.0}{0.3} \right)^2 \approx 170.74 \rightarrow 171
\]

**Sample Size Table for Different Scenarios**:
| ME   | Confidence | σ   | Required n |
|------|------------|-----|------------|
| 0.3  | 95%        | 2.0 | 171        |
| 0.5  | 95%        | 2.0 | 62         |
| 0.3  | 99%        | 2.0 | 295        |
| 0.2  | 95%        | 2.0 | 384        |

### **Visualization**
```plaintext
Line Chart: Required Sample Size vs. Margin of Error
X-axis: Margin of Error (0.1 to 1.0)
Y-axis: Required Sample Size (log scale)
Multiple lines for different confidence levels (90%, 95%, 99%).
```
- **Interpretation**: As the desired margin of error decreases, the required sample size increases exponentially. Higher confidence levels also require larger samples.

### **Key Insights & Decision Implications**
- **Insight**: A sample of 171 employees is sufficient to estimate the mean satisfaction within ±0.3 points with 95% confidence. Stratification by department may reduce required size.
- **Decision**: Use an interactive sample size calculator in the survey planning dashboard. Input parameters (population size, confidence level, margin of error, estimated variability) to get recommended sample sizes and associated costs. This ensures cost-effective yet precise surveys.

---

## **Use Case 4: Estimating Average User Engagement Time with Unknown σ**

### **Concept & Purpose**
- **Statistical Concept**: Confidence interval for a population mean when the population standard deviation is unknown, using the t-distribution.
- **Purpose**: Estimate the average time users spend on a new mobile app feature. No prior data is available, so the sample standard deviation is used.
- **Assumptions**:
  - The sample is random.
  - The population is approximately normally distributed (robust to moderate violations if n ≥ 30).
  - No extreme outliers.

### **Application in Tech**
A startup launches a new feature and wants to estimate the average time users spend on it. A random sample of 25 users is tracked, yielding a sample mean of 8.2 minutes and a sample standard deviation of 2.5 minutes.

### **Structured Data & Calculations**
- Sample size (n): 25
- Sample mean (\(\bar{x}\)): 8.2 minutes
- Sample standard deviation (s): 2.5 minutes
- Confidence level: 95%
- Degrees of freedom (df): n - 1 = 24
- t* for 95% CI with df=24: 2.064 (from t-table)

**Standard error (SE)**:  
\[
SE = \frac{s}{\sqrt{n}} = \frac{2.5}{\sqrt{25}} = 0.5
\]

**Margin of error (ME)**:  
\[
ME = t^* \times SE = 2.064 \times 0.5 \approx 1.032
\]

**95% Confidence Interval**:  
\[
\bar{x} \pm ME = 8.2 \pm 1.032 = [7.168, 9.232]
\]

**t-Distribution Critical Values Table**:
| Confidence Level | df=10 | df=24 | df=30 | df=∞ (z) |
|------------------|-------|-------|-------|----------|
| 90%              | 1.812 | 1.711 | 1.697 | 1.645    |
| 95%              | 2.228 | 2.064 | 2.042 | 1.960    |
| 99%              | 3.169 | 2.797 | 2.750 | 2.576    |

### **Visualization**
```plaintext
t-Distribution (df=24) vs. Normal Distribution:
X-axis: Sample mean engagement time (minutes)
Y-axis: Probability density
t-distribution (blue) with thicker tails; normal distribution (black).
Shaded area between 7.168 and 9.232 represents 95% CI.
```
- **Interpretation**: We are 95% confident that the true population mean engagement time lies between 7.168 and 9.232 minutes. The t-distribution accounts for extra uncertainty due to estimating σ.

### **Key Insights & Decision Implications**
- **Insight**: The interval is wider than if σ were known, reflecting added uncertainty. The estimate suggests moderate user engagement.
- **Decision**: Use this CI to decide whether to invest further in the feature. Create a dashboard that updates the CI as more data comes in, and alerts when the CI excludes a target threshold (e.g., 10 minutes).

---

## **Use Case 5: Impact of Confidence Level on Drug Efficacy Estimation**

### **Concept & Purpose**
- **Statistical Concept**: How confidence level (90%, 95%, 99%) affects the width of a confidence interval for a mean.
- **Purpose**: Report the estimated improvement in patient recovery time due to a new drug, and illustrate the trade-off between confidence and precision.
- **Assumptions**:
  - The sample is random and representative.
  - The population standard deviation is known or estimated.
  - The sampling distribution is approximately normal.

### **Application in Pharmaceuticals**
A clinical trial tests a new drug on 50 patients. The mean reduction in recovery time is 3.2 days with a standard deviation of 1.8 days. Calculate and compare 90%, 95%, and 99% confidence intervals.

### **Structured Data & Calculations**
- Sample size (n): 50
- Sample mean (\(\bar{x}\)): 3.2 days
- Sample standard deviation (s): 1.8 days (used as estimate of σ)
- Standard error (SE): \(1.8 / \sqrt{50} \approx 0.2546\)

**Critical values**:
- 90% CI: z* = 1.645
- 95% CI: z* = 1.96
- 99% CI: z* = 2.576

**Confidence Intervals**:
| Confidence Level | Margin of Error | CI Lower | CI Upper | Width    |
|------------------|-----------------|----------|----------|----------|
| 90%              | 0.4188          | 2.7812   | 3.6188   | 0.8376   |
| 95%              | 0.4989          | 2.7011   | 3.6989   | 0.9978   |
| 99%              | 0.6557          | 2.5443   | 3.8557   | 1.3114   |

### **Visualization**
```plaintext
Bar Chart: Confidence Intervals for Different Confidence Levels
X-axis: Confidence Level (90%, 95%, 99%)
Y-axis: Mean reduction (days)
Bars represent point estimate (3.2) with error bars showing the CI.
```
- **Interpretation**: As confidence level increases, the interval widens. The 99% CI is the widest, reflecting greater certainty that it contains the true mean, but at the cost of precision.

### **Key Insights & Decision Implications**
- **Insight**: The drug shows a statistically significant reduction (all CIs are above zero). Higher confidence yields more conservative estimates.
- **Decision**: Choose the confidence level based on stakeholder risk tolerance. For regulatory submissions, a 95% CI is standard. For internal decisions, a 90% CI might suffice. Develop an interactive tool that allows adjusting the confidence level and instantly updates the CI, helping communicate uncertainty.

---

## **Use Case 6: Estimating Conversion Rate for a Marketing Campaign**

### **Concept & Purpose**
- **Statistical Concept**: Confidence interval for a proportion, with sample size determination for a desired margin of error.
- **Purpose**: Estimate the conversion rate (proportion of clicks leading to purchases) of a new online ad campaign and plan future sample sizes.
- **Assumptions**:
  - The sample is a random subset of visitors.
  - The sample size is large enough: \(n\hat{p} \geq 15\) and \(n(1-\hat{p}) \geq 15\).
  - The normal approximation is valid.

### **Application in Digital Marketing**
A company runs an ad campaign for 1 week. Out of 2,000 clicks, 120 resulted in purchases. They want to estimate the conversion rate with 95% confidence and determine the sample size needed for a future campaign to achieve a margin of error of ±1%.

### **Structured Data & Calculations**
- Sample size (n): 2,000
- Conversions (x): 120
- Sample proportion (\(\hat{p}\)): \(120/2000 = 0.06\)
- Confidence level: 95% → z* = 1.96

**Standard error (SE)**:  
\[
SE = \sqrt{\frac{0.06 \times 0.94}{2000}} \approx 0.0053
\]

**Margin of error (ME)**:  
\[
ME = 1.96 \times 0.0053 \approx 0.0104
\]

**95% Confidence Interval**:  
\[
\hat{p} \pm ME = 0.06 \pm 0.0104 = [0.0496, 0.0704]
\]

**Sample size needed for ME = 0.01 (1%)**:
Using conservative \(\hat{p} = 0.5\):
\[
n = \frac{(z^*)^2 \times \hat{p}(1-\hat{p})}{ME^2} = \frac{1.96^2 \times 0.5 \times 0.5}{0.01^2} = 9604
\]
Using \(\hat{p} = 0.06\):
\[
n = \frac{1.96^2 \times 0.06 \times 0.94}{0.01^2} \approx 2167
\]

### **Visualization**
```plaintext
Normal Distribution for Sample Proportion:
X-axis: Conversion rate (0.04 to 0.08)
Y-axis: Probability density
Vertical line at sample proportion 0.06; shaded area between 0.0496 and 0.0704 represents 95% CI.
```
- **Interpretation**: We are 95% confident that the true conversion rate is between 4.96% and 7.04%. The margin of error is ±1.04 percentage points.

### **Key Insights & Decision Implications**
- **Insight**: The conversion rate is likely between 5% and 7%, which may meet the target of 5%. For a more precise estimate (±1%), a sample size of about 2,167 clicks is needed if the proportion is near 6%, but a conservative approach would require 9,604 clicks.
- **Decision**: Use the CI to evaluate campaign success. Build an A/B testing dashboard that computes CIs for different campaigns and recommends sample sizes for future tests based on desired precision and confidence.

---

## **Summary**
These six use cases demonstrate how confidence intervals are applied in business, finance, and research. Each case includes:
- Clear statistical explanations and assumptions.
- Practical applications with realistic scenarios.
- Structured tables and visualizations.
- Key insights and actionable decision frameworks.

By leveraging confidence intervals, organizations can make data-driven decisions, quantify uncertainty, and optimize resource allocation. Interactive dashboards and sample size calculators enhance real-time decision-making and strategic planning.
