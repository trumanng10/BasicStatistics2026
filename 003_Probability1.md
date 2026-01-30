### **Use Case 1: Recognizing Randomness – The Gambler’s Fallacy**  
**Concept:** Humans tend to see patterns in random sequences (apophenia) and incorrectly believe that past independent events influence future ones.  
**Example:** Coin tosses.  
**Explanation:** After 4 consecutive heads, many believe the next toss is more likely to be tails. However, each toss is independent with \( P(\text{Heads}) = 0.5 \).  
**Illustration:**  
Table of observed vs. expected runs in 100 tosses:

| Consecutive Heads | Observed Frequency | Expected Frequency (if random) |
|-------------------|--------------------|--------------------------------|
| 3 in a row        | 12                 | ~12.5                          |
| 4 in a row        | 6                  | ~6.25                          |
| 5 in a row        | 3                  | ~3.13                          |

**Graph:** A bar chart comparing observed vs. expected runs shows clustering similar to random patterns.  
**Takeaway:** Random sequences naturally exhibit clusters; independence means past does not affect future outcomes.

---

### **Use Case 2: Law of Large Numbers – Dice Rolling Simulation**  
**Concept:** As sample size increases, the relative frequency of an event converges to its theoretical probability.  
**Example:** Rolling a fair die.  
**Explanation:** The proportion of sixes approaches \( 1/6 \) as the number of rolls increases.  
**Illustration:**  
Table of cumulative proportion of sixes:

| Number of Rolls | Cumulative Proportion of Sixes |
|-----------------|--------------------------------|
| 10              | 0.200                          |
| 50              | 0.180                          |
| 100             | 0.160                          |
| 500             | 0.168                          |
| 1000            | 0.166                          |

**Graph:** A line plot showing the proportion stabilizing near 0.1667.  
**Takeaway:** Small samples vary widely; large samples provide reliable probability estimates.

---

### **Use Case 3: Tree Diagram – Sequential Decision under Uncertainty**  
**Concept:** Tree diagrams map all possible outcomes of sequential random events, enabling probability calculations.  
**Example:** Beach stand with 3 customers, 2 soft drinks (S), 1 ice cream (I).  
**Explanation:** Each customer chooses S or I with equal probability unless drinks are sold out.  
**Illustration:**  
Tree diagram branches with probabilities:

- Path probabilities calculated by multiplying along branches.
- Event "At least one drink left for you" = sum of probabilities of favorable paths = 0.5.

**Table of Path Probabilities:**

| Path (Customer Choices) | Probability |
|--------------------------|-------------|
| I-I-I                    | 0.125       |
| I-I-S                    | 0.125       |
| I-S-I                    | 0.125       |
| I-S-S                    | 0.125       |
| S-I-I                    | 0.125       |
| S-I-S                    | 0.125       |
| S-S-I                    | 0.125       |

**Takeaway:** Tree diagrams clarify complex sequential problems and allow systematic probability calculation.

---

### **Use Case 4: Mutually Exclusive & Collectively Exhaustive Events – Venn Diagrams**  
**Concept:** Events are disjoint (mutually exclusive) if they cannot occur together; they are collectively exhaustive if they cover all possible outcomes.  
**Example:** Rolling a die: events A = {1,2}, B = {3,4}, C = {5,6}.  
**Explanation:** A, B, C are disjoint and together form the sample space {1,2,3,4,5,6}.  
**Illustration:**  
Venn diagram with non-overlapping circles inside a rectangle (sample space).  
**Table of Probabilities:**

| Event | Outcomes | Probability |
|-------|----------|-------------|
| A     | {1,2}    | 1/3         |
| B     | {3,4}    | 1/3         |
| C     | {5,6}    | 1/3         |
| Total | {1..6}   | 1           |

**Takeaway:** Disjoint events simplify probability addition; collectively exhaustive events ensure total probability = 1.

---

### **Use Case 5: Joint & Marginal Probabilities – Contingency Table Analysis**  
**Concept:** Joint probabilities show the intersection of two variables; marginal probabilities show distributions of single variables.  
**Example:** Beach visitors by activity (Rest, Play, Swim) and gender (M, F).  
**Illustration:**  
Contingency table with joint and marginal probabilities (based on PDF 308):

|          | Male (M) | Female (F) | Marginal (Activity) |
|----------|----------|------------|---------------------|
| Rest (R) | 0.30     | 0.40       | 0.70                |
| Play (P) | 0.10     | 0.10       | 0.20                |
| Swim (S) | 0.05     | 0.05       | 0.10                |
| Marginal (Gender) | 0.45 | 0.55       | 1.00                |

**Graph:** Stacked bar chart showing joint distributions.  
**Takeaway:** Marginal probabilities sum from joint probabilities; joint probabilities sum to 1.

---

### **Use Case 6: Conditional Probability & Bayes’ Theorem – Updating Beliefs**  
**Concept:** Conditional probability revises the likelihood of an event given new evidence; Bayes’ theorem formalizes this update.  
**Example:** Probability a person is swimming given they are female.  
**Given data from Use Case 5:**  
- \( P(\text{F}) = 0.55 \)  
- \( P(\text{S} \cap \text{F}) = 0.05 \)  
- \( P(\text{S} | \text{F}) = \frac{0.05}{0.55} \approx 0.091 \)  

**Bayes’ Theorem Application:**  
Suppose we want \( P(\text{F} | \text{S}) \):  
\[
P(\text{F} | \text{S}) = \frac{P(\text{S} | \text{F}) \cdot P(\text{F})}{P(\text{S})} = \frac{0.091 \times 0.55}{0.10} \approx 0.50
\]

**Table of Conditional Probabilities:**

| Condition | \( P(\text{R}|\cdot) \) | \( P(\text{P}|\cdot) \) | \( P(\text{S}|\cdot) \) |
|-----------|--------------------------|--------------------------|--------------------------|
| Given Male   | 0.667                   | 0.222                   | 0.111                   |
| Given Female | 0.727                   | 0.182                   | 0.091                   |

**Takeaway:** Conditional probability refines predictions; Bayes’ theorem integrates prior knowledge with new data.

---

These **6 use cases** bridge theoretical concepts from the PDFs to practical applications, enhancing understanding of randomness, probability rules, and statistical reasoning. Each case includes visual or tabular aids to reinforce learning.
