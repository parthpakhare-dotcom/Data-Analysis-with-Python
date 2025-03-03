# **Chi-Square Test for Categorical Variables**  

The Chi-Square (_X^2_)) test is specifically used for categorical variables. It evaluates whether the frequencies of observed outcomes significantly deviate from expected frequencies, assuming the variables are independent. The test is grounded in the chi-square distribution, which is applied to count data and helps determine if any observed deviations could have arisen by random chance.  

The chi-square method involves forming two hypotheses:  

### **1) Null Hypothesis (_H0_)**  
This assumes that there is no correlation between the variables and any noticeable difference is just a random coincidence.  

### **2) Alternative Hypothesis (H<sub>a</sub>)**  
This assumes that there is an appreciable difference between the observed and expected values, suggesting that there must be some correlation between both variables.  

At the end, we always check whether to reject or fail to reject _H0_ —not directly _Ha_.  

### **Why Do We Always Check ?**  
- Statistical tests assume _H0_ is true by default.  
  - This is like "innocent until proven guilty" in court.  
  - We need strong evidence to reject _H0_.  
- We use probability to check how likely our data is under _H0_.  
  - If the data is very unlikely under _H0_ (small p-value), we reject it.  
  - If the data is not unlikely, we don’t reject _H0_ (but we don’t confirm it either).  
- We never “accept” _H0_, only reject _H0_.  
  - Failing to reject _H0_ does not prove _H0_ is true—it only means there’s not enough evidence against it.  
  - If we reject _H0_, we take _Ha_ as the best explanation for now, but future studies might refine it.  

A chi-square test checks whether the deviation between observed and expected frequencies is **just random** or if there is a significant relationship.  

### **How Does the Chi-Square Test Work?**  
✔ It compares actual results (**observed values**) with what we would expect (**expected values**) under the assumption of independence.  
✔ If the difference is small, it’s just random variation.  
✔ If the difference is large, the chi-square test gives a low p-value, meaning the relationship is likely not random.  

---

## **Chi-Square Test Formula**  

The chi-square statistic is calculated using the formula:  

\[
chi^2 or _X^2_ = ∑ [(Oi - Ei)^2 / Ei ]
\]

Where:  
- \(O\) = Observed frequency  
- \(E\) = Expected frequency  

Each expected frequency (\(E\)) in a contingency table is calculated as:  

![image](https://github.com/user-attachments/assets/7d45133e-6663-49a7-8b2c-777ac907d63a)


---

## **Determining the Critical Value**  

A critical value is a threshold that helps us decide whether to reject or fail to reject the null hypothesis (\(H_0\)) in hypothesis testing.  

To determine it, we need:  
- **Significance Level (\(\alpha\))**: Usually 0.05 (5%) or 0.01 (1%).  
- **Degrees of freedom (\(df\))**: Determines which row in the table to use.  

### **Degrees of Freedom Formula**  

\[
df = (r - 1) x (c - 1)
\]

where:  
- \(r\) = Number of rows in the contingency table  
- \(c\) = Number of columns in the contingency table  

---

# **Chi-Square Test Example**  

## **Step 1: Observed Data Table**  

A researcher collects data on 200 individuals and categorizes them into **Smoker/Non-Smoker** and whether they have **Disease/No Disease**:  

| Category    | Disease | No Disease | Total |
|------------|---------|------------|-------|
| Smoker     | 50      | 30         | 80    |
| Non-Smoker | 30      | 100        | 130   |
| **Total**  | **80**  | **130**    | **200** |

### **Observed Frequencies (O)**  
- **Smokers with disease** = 50  
- **Smokers without disease** = 30  
- **Non-smokers with disease** = 30  
- **Non-smokers without disease** = 100  

---

## **Step 2: Calculate Expected Frequencies (E)**  

Using the formula:  

\[
\E = (Row Total × Column Total) / Grand Total
\]

For each cell:  

1. **Smoker, Disease**  
   \[
   E = 80 x 80 / 200 = 32
   \]

2. **Smoker, No Disease**  
   \[
   E = 80 x 130 /200 = 52
   \]

3. **Non-Smoker, Disease**  
   \[
   E = 120 x 80 /200 = 48
   \]

4. **Non-Smoker, No Disease**  
   \[
   E = 120 x 130 / 200 = 78
   \]

---

## **Step 3: Calculate the Chi-Square Statistic**  

\[
\chi² = ∑ [(O - E)² / E]
\]

For each cell:  

1. **Smoker, Disease**  
   \[
   \(50 - 32)² / 32 = 324 / 32 = 10.125
   \]

2. **Smoker, No Disease**  
   \[
   \(30 - 52)² / 52 = 484 / 52 = 9.31
   \]

3. **Non-Smoker, Disease**  
   \[
   \(30 - 48)² / 48 = 324 / 48 = 6.75
   \]

4. **Non-Smoker, No Disease**  
   \[
   \(100 - 78)² / 78 = 484 / 78 = 6.21
   \]

Summing these values:  

\[
\chi² = 10.125 + 9.31 + 6.75 + 6.21 = 32.395
\]

---

## **Step 4: Find Degrees of Freedom (df)**  

\[
df = (r - 1) × (c - 1) = (2 - 1) × (2 - 1) = 1
\]

---

## **Step 5: Finding the Critical Value**  

From the **Chi-Square Table**, for **\( df = 1 \)** and **\( \alpha = 0.05 \)**:

| df  | 0.10  | 0.05  | 0.01  |
|-----|-------|-------|-------|
| 1   | 2.706 | 3.841 | 6.635 |

The **critical value = 3.841**.

(_Note that the critical table is seperately calculated and calculating directly with formulas is a bit long process; there are pyton methods for that. Here, we are just taking the intended first row of the chi square table to find the critical value at row 1 for significant value 0.05.

---

## **Step 6: Compare With Our Chi-Square Statistic**  

\[
\chi^2 = 32.395
\]

Since:

\[
32.395 > 3.841
\]

We **reject the null hypothesis (_H0_)**.

---

## **Final Interpretation**  

Since our calculated chi-square statistic (32.395) **exceeds** the critical value (3.841), the difference is **not due to random chance**.  

Thus, we conclude that **smoking is significantly associated with disease**.

---

### **Summary**  
✅ **If \( \chi^2 \) > critical value** → **Reject _H0_** → Significant relationship.  
❌ **If \( \chi^2 \) < critical value** → **Fail to reject _H0_** → No significant relationship.  
