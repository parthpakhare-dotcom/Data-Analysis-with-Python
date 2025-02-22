# **Chi-Square Test for Categorical Variables**  

The Chi-Square (\(\chi^2\)) test is specifically used for categorical variables. It evaluates whether the frequencies of observed outcomes significantly deviate from expected frequencies, assuming the variables are independent. The test is grounded in the chi-square distribution, which is applied to count data and helps determine if any observed deviations could have arisen by random chance.  

The chi-square method involves forming two hypotheses:  

### **1) Null Hypothesis (H<sub>0</sub>)**  
This assumes that there is no correlation between the variables and any noticeable difference is just a random coincidence.  

### **2) Alternative Hypothesis (H<sub>a</sub>)**  
This assumes that there is an appreciable difference between the observed and expected values, suggesting that there must be some correlation between both variables.  

At the end, we always check whether to reject or fail to reject \(H_0\)​—not directly \(H_a\).  

### **Why Do We Always Check \(H_0\)?**  
- Statistical tests assume \(H_0\) is true by default.  
  - This is like "innocent until proven guilty" in court.  
  - We need strong evidence to reject \(H_0\).  
- We use probability to check how likely our data is under \(H_0\).  
  - If the data is very unlikely under \(H_0\) (small p-value), we reject it.  
  - If the data is not unlikely, we don’t reject \(H_0\) (but we don’t confirm it either).  
- We never “accept” \(H_a\), only reject \(H_0\).  
  - Failing to reject \(H_0\) does not prove \(H_0\) is true—it only means there’s not enough evidence against it.  
  - If we reject \(H_0\), we take \(H_a\) as the best explanation for now, but future studies might refine it.  

A chi-square test checks whether the deviation between observed and expected frequencies is **just random** or if there is a significant relationship.  

### **How Does the Chi-Square Test Work?**  
✔ It compares actual results (**observed values**) with what we would expect (**expected values**) under the assumption of independence.  
✔ If the difference is small, it’s just random variation.  
✔ If the difference is large, the chi-square test gives a low p-value, meaning the relationship is likely not random.  

---

## **Chi-Square Test Formula**  

The chi-square statistic is calculated using the formula:  

\[
\chi^2 = \sum \frac{(O - E)^2}{E}
\]

Where:  
- \(O\) = Observed frequency  
- \(E\) = Expected frequency  

Each expected frequency (\(E\)) in a contingency table is calculated as:  

\[
E = \frac{\text{(Row Total)} \times \text{(Column Total)}}{\text{Grand Total}}
\]

---

## **Determining the Critical Value**  

A critical value is a threshold that helps us decide whether to reject or fail to reject the null hypothesis (\(H_0\)) in hypothesis testing.  

To determine it, we need:  
- **Significance Level (\(\alpha\))**: Usually 0.05 (5%) or 0.01 (1%).  
- **Degrees of freedom (\(df\))**: Determines which row in the table to use.  

### **Degrees of Freedom Formula**  

\[
df = (r - 1) \times (c - 1)
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
E = \frac{(\text{Row Total}) \times (\text{Column Total})}{\text{Grand Total}}
\]

For each cell:  

1. **Smoker, Disease**  
   \[
   E = \frac{80 \times 80}{200} = 32
   \]

2. **Smoker, No Disease**  
   \[
   E = \frac{80 \times 130}{200} = 52
   \]

3. **Non-Smoker, Disease**  
   \[
   E = \frac{120 \times 80}{200} = 48
   \]

4. **Non-Smoker, No Disease**  
   \[
   E = \frac{120 \times 130}{200} = 78
   \]

---

## **Step 3: Calculate the Chi-Square Statistic**  

\[
\chi^2 = \sum \frac{(O - E)^2}{E}
\]

For each cell:  

1. **Smoker, Disease**  
   \[
   \frac{(50 - 32)^2}{32} = \frac{324}{32} = 10.125
   \]

2. **Smoker, No Disease**  
   \[
   \frac{(30 - 52)^2}{52} = \frac{484}{52} = 9.31
   \]

3. **Non-Smoker, Disease**  
   \[
   \frac{(30 - 48)^2}{48} = \frac{324}{48} = 6.75
   \]

4. **Non-Smoker, No Disease**  
   \[
   \frac{(100 - 78)^2}{78} = \frac{484}{78} = 6.21
   \]

Summing these values:  

\[
\chi^2 = 10.125 + 9.31 + 6.75 + 6.21 = 32.395
\]

---

## **Step 4: Find Degrees of Freedom (df)**  

\[
df = (r - 1) \times (c - 1) = (2 - 1) \times (2 - 1) = 1
\]

---

## **Step 5: Finding the Critical Value**  

From the **Chi-Square Table**, for **\( df = 1 \)** and **\( \alpha = 0.05 \)**:

| df  | 0.10  | 0.05  | 0.01  |
|-----|-------|-------|-------|
| 1   | 2.706 | 3.841 | 6.635 |

The **critical value = 3.841**.

---

## **Step 6: Compare With Our Chi-Square Statistic**  

\[
\chi^2 = 32.395
\]

Since:

\[
32.395 > 3.841
\]

We **reject the null hypothesis (\(H_0\))**.

---

## **Final Interpretation**  

Since our calculated chi-square statistic (32.395) **exceeds** the critical value (3.841), the difference is **not due to random chance**.  

Thus, we conclude that **smoking is significantly associated with disease**.

---

### **Summary**  
✅ **If \( \chi^2 \) > critical value** → **Reject \( H_0 \)** → Significant relationship.  
❌ **If \( \chi^2 \) < critical value** → **Fail to reject \( H_0 \)** → No significant relationship.  
