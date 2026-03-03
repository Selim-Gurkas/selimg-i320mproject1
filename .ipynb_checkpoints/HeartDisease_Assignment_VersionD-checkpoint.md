# Week 3 Assignment: Heart Disease Dataset Analysis

## I 320D: Data Science for Biomedical Informatics | Spring 2026

### 📋 Assignment Version D

---

## 🎯 This Week's Mantra

> **"Every Column Tells a Story"**

In this assignment, you'll apply the 10-Point Data Inspection to a real-world healthcare dataset focused on heart disease diagnosis. By the end, you'll understand not just *what* the data contains, but *why* each variable matters for clinical decision-making.

---

## Learning Objectives

By completing this assignment, you will be able to:

1. ✅ Apply the systematic 10-Point Inspection to a new healthcare dataset
2. ✅ Identify and classify feature types (continuous, discrete, categorical, ordinal)
3. ✅ Detect and document data quality issues (missing values, unexpected values)
4. ✅ Research and document clinical meaning for healthcare variables
5. ✅ Create meaningful data groupings based on clinical standards
6. ✅ Formulate answerable research questions about heart disease risk factors

---

## About the Dataset

**Dataset:** Heart Disease UCI (Combined)  
**Source:** UCI Machine Learning Repository / Kaggle  
**File:** `heart_disease_uci.csv`  
**Target Variable:** `num` (diagnosis of heart disease: 0 = no disease, 1-4 = presence of disease)

### Clinical Context

Heart disease remains the leading cause of death globally, accounting for approximately 17.9 million deaths annually according to the World Health Organization. This dataset combines patient records from four medical institutions: Cleveland Clinic, Hungarian Institute of Cardiology, University Hospital Zurich (Switzerland), and VA Long Beach Medical Center. Understanding these diagnostic variables is crucial for:

- Early identification of high-risk patients
- Understanding regional variations in heart disease presentation
- Clinical decision support systems
- Risk stratification and preventive care planning

---

## Getting Started

First, load the dataset and import your libraries:

```python
# Import libraries


# Load the dataset


# Display first few rows to confirm it loaded

```

---

## Part 1: The 10-Point Data Inspection (40 points)

Complete each inspection step and document your findings.

### Step 1: Shape (4 points)

**Your Code:**
```python

```

**Your Findings:**
- How many rows (observations)? _______________
- How many columns (features)? _______________
- What does each row represent in clinical terms? _______________

---

### Step 2: Column Names (4 points)

**Your Code:**
```python

```

**Your Findings:**
- List all column names:

- Which columns might need further research to understand? (Hint: Many use medical abbreviations!)

---

### Step 3: Data Types (4 points)

**Your Code:**
```python

```

**Your Findings:**
- Which columns are numeric (int64 or float64)?

- Which columns are categorical (object/string)?

- Are there any data types that seem incorrect based on what you know about the data?

---

### Step 4: First Look (4 points)

**Your Code:**
```python

```

**Your Findings:**
- What do the actual values look like?

- Do you notice any categorical variables that are already human-readable vs. encoded?

- Are there any values that look like they might be placeholders for missing data?

---

### Step 5: Last Look (4 points)

**Your Code:**
```python

```

**Your Findings:**
- Does the data end cleanly?

- Are the last rows consistent with the first rows?

- Do you notice more or fewer missing values in later rows?

---

### Step 6: Memory Usage (4 points)

**Your Code:**
```python

```

**Your Findings:**
- How much memory does the dataset use? _______________ MB
- Is this a "small" or "large" dataset by data science standards?

---

### Step 7: Missing Values (4 points)

**Your Code:**
```python

```

**Your Findings:**
- Which columns have missing values?

- What percentage of each column is missing?

- Which columns have the MOST missing data? What might explain this?

---

### Step 8: Duplicates (4 points)

**Your Code:**
```python

```

**Your Findings:**
- Are there any duplicate rows? _______________
- Are all patient IDs unique? _______________

---

### Step 9: Basic Statistics (4 points)

**Your Code:**
```python

```

**Your Findings:**
- What is the age range in the dataset? _______________ to _______________
- What is the range of resting blood pressure (trestbps)? _______________ to _______________
- What is the range of serum cholesterol (chol)? _______________ to _______________
- What is the range of maximum heart rate achieved (thalch)? _______________ to _______________
- Do any min/max values seem impossible or clinically unlikely?

---

### Step 10: Unique Counts (4 points)

**Your Code:**
```python

```

**Your Findings:**
- Which columns have very few unique values (likely categorical)?

- Which columns have many unique values (likely continuous or IDs)?

- Does the number of unique IDs match the number of rows? _______________

---

## Part 2: Data Dictionary (20 points)

Complete the following data dictionary. For each column, you must:
1. **Research** the clinical meaning (these are standard cardiac assessment terms)
2. **Identify** the feature type (Continuous, Discrete, Categorical-Nominal, Categorical-Ordinal, Binary, Identifier)
3. **Document** the valid values/range you observe
4. **Note** any issues or questions

| Column | Description | Feature Type | Valid Values/Range | Notes/Issues |
|--------|-------------|--------------|-------------------|--------------|
| `id` | | | | |
| `age` | | | | |
| `sex` | | | | |
| `dataset` | | | | |
| `cp` | | | | |
| `trestbps` | | | | |
| `chol` | | | | |
| `fbs` | | | | |
| `restecg` | | | | |
| `thalch` | | | | |
| `exang` | | | | |
| `oldpeak` | | | | |
| `slope` | | | | |
| `ca` | | | | |
| `thal` | | | | |
| `num` | | | | |

### Clinical Research Questions for Version D

Answer these questions based on your research (you may need to use Google):

**1. How is maximum heart rate (thalch) measured during a cardiac stress test? What is the formula for calculating age-predicted maximum heart rate, and why is achieving a target percentage important?**

Your answer:

---

**2. What is ST depression (oldpeak)? Why is the amount of ST depression during exercise an important diagnostic indicator for coronary artery disease?**

Your answer:

---

**3. What are the different types of chest pain (cp) in this dataset? Which type is most commonly associated with heart disease, and why might "asymptomatic" patients still be tested?**

Your answer:

---

**4. What is chronotropic incompetence? How might a patient's inability to achieve their target heart rate during exercise testing indicate underlying heart disease?**

Your answer:

---

## Part 3: Data Validation (15 points)

### 3.1 Blood Pressure Validation (5 points)

Write code to check:
- How many blood pressure readings are 0? (This is clinically impossible for a living patient!)
- How many readings are below 80 mmHg? Above 200 mmHg?
- What might a value of 0 represent in this dataset?

**Your Code:**
```python

```

**Your Findings:**

- Are there any impossible blood pressure values?

- How should values of 0 be treated - as missing data or as valid values?

- Does this match what `.isnull()` reports for this column?

---

### 3.2 Cholesterol Validation (5 points)

Write code to examine cholesterol values closely. Check for any unusual values including zeros.

**Your Code:**
```python

```

**Your Findings:**

- Did you find any cholesterol values of 0?

- Is a cholesterol level of 0 clinically possible?

- How many such impossible values exist?

- What would happen if you calculated the mean cholesterol without handling this?

---

### 3.3 Multi-Source Data Validation (5 points)

This dataset combines data from four different medical centers. Write code to:
1. Count patients from each source (dataset column)
2. Check if missing data patterns differ by source

**Your Code:**
```python

```

**Your Findings:**

- Which medical center contributed the most patients?

- Which medical center contributed the fewest?

- Do certain columns have more missing data in certain sources? Which ones?

- Why might data completeness vary across medical institutions?

---

## Part 4: Create Heart Rate Response Groups (10 points)

Create a new column called `hr_response` that categorizes patients based on their maximum heart rate achieved (thalch) during stress testing, relative to their age-predicted maximum.

### Version D: Heart Rate Response Categories

First, you'll need to calculate each patient's **age-predicted maximum heart rate** using the formula:
```
Age-Predicted Max HR = 220 - age
```

Then calculate what **percentage of their maximum** they achieved:
```
Percent of Max = (thalch / Age-Predicted Max HR) * 100
```

Use these categories based on stress test interpretation guidelines:

| HR Response Category | Percent of Age-Predicted Max | Clinical Significance |
|---------------------|------------------------------|----------------------|
| Missing/Invalid | thalch is NaN or 0 | Data quality issue - cannot classify |
| Poor Response | < 70% | Possible chronotropic incompetence |
| Submaximal | 70-84% | Below diagnostic threshold |
| Adequate | 85-99% | Diagnostically valid test |
| Excellent | ≥ 100% | Exceeded predicted maximum |

### Your Code:

```python
# Step 1: Calculate age-predicted maximum heart rate


# Step 2: Calculate percentage of maximum achieved


# Step 3: Create the hr_response category column
# IMPORTANT: Handle missing/zero thalch values appropriately


```

### Verify your groupings worked:

```python
# Show counts per heart rate response category

```

### Calculate heart disease rate by heart rate response:

```python
# Create a binary indicator for heart disease (num > 0 means disease present)
# Then calculate the percentage of patients with heart disease in each HR response category
# Exclude the "Missing/Invalid" category from your interpretation

```

### Analysis Questions:

**1. How many patients are in each heart rate response category? How many have missing/invalid heart rate readings?**

Your answer:

---

**2. What is the heart disease rate (percentage) for each heart rate response category (excluding invalid)?**

Your answer:

---

**3. Does heart disease prevalence vary with heart rate response as expected? Patients who can't achieve their target heart rate often have cardiac issues - do you see this pattern?**

Your answer:

---

## Part 5: Research Questions (15 points)

### 5.1 Write Three Answerable Questions (9 points)

Write three questions that THIS dataset can answer. Remember: the data can show relationships and patterns, but cannot prove causation.

**Your questions must explore these specific areas:**

1. **A question about thallium stress test results (thal) and heart disease:**


---

2. **A question comparing patients across the four medical centers (dataset):**


---

3. **A question about the combination of ST depression (oldpeak) AND ST slope (slope):**


---

### 5.2 Identify One Question the Data CANNOT Answer (3 points)

Write one question about **patient symptoms or quality of life** that this dataset cannot answer, and explain why.

**Question:**


**Why it cannot be answered with this data:**


---

### 5.3 Grouping Analysis (3 points)

Answer this question using a groupby analysis:

**"What is the average age for each value of the number of major vessels colored by fluoroscopy (ca)?"**

(Note: You'll need to handle missing values in ca - about 66% of this column is missing!)

**Your Code:**
```python

```

**Your Interpretation:**

Is there a relationship between age and number of diseased vessels? Does this make clinical sense? What are the limitations of this analysis given the high missingness in the ca column?


---

## Part 6: Target Variable Analysis (Bonus - 5 points)

The `num` column is our **target variable** - what we're trying to predict. It has 5 possible values (0-4) representing the severity of heart disease narrowing. Analyze its distribution.

**Your Code:**
```python
# Show the count and percentage for each value of num

# Also create a binary version (0 = no disease, 1 = disease present) and show its distribution

```

### Bonus Questions:

**1. What percentage of patients in this dataset have some form of heart disease (num > 0)?**

Your answer:

---

**2. Is this dataset balanced or imbalanced between disease/no disease?**

Your answer:

---

**3. Looking at the 5 severity levels (0-4), which level is most common? Is this distribution what you'd expect clinically?**

Your answer:

---

**4. How might the multi-severity nature of the target (0-4) versus a simple binary (disease/no disease) affect how you'd approach a machine learning problem?**

Your answer:

---

## Submission Checklist

Before submitting, verify you have completed:

- [ ] **Part 1:** All 10 inspection steps with code AND written findings
- [ ] **Part 2:** Complete data dictionary with all 16 columns filled in
- [ ] **Part 2:** Answered all 4 clinical research questions
- [ ] **Part 3:** All 3 validation checks with code and answers
- [ ] **Part 4:** Created `hr_response` column using **Heart Rate Response Categories**
- [ ] **Part 4:** Calculated heart disease rate by HR response with interpretation
- [ ] **Part 5:** Three research questions (thal, medical centers, oldpeak+slope)
- [ ] **Part 5:** One unanswerable question about symptoms/quality of life
- [ ] **Part 5:** Age by number of vessels (ca) groupby analysis
- [ ] **Bonus (Optional):** Target variable analysis

---

## Grading Rubric

| Component | Points | Requirements for Full Credit |
|-----------|--------|------------------------------|
| Part 1: 10-Point Inspection | 40 | All 10 steps complete with working code AND thoughtful written analysis |
| Part 2: Data Dictionary | 20 | All 16 columns documented with correct feature types and clinical research |
| Part 3: Data Validation | 15 | All validation checks complete with working code and insightful answers |
| Part 4: HR Response Categories | 10 | Working code that correctly calculates % of max HR and creates categories (including invalid handling) AND meaningful interpretation |
| Part 5: Research Questions | 15 | Three good questions in specified areas, one clear limitation, groupby analysis complete |
| **Bonus:** Target Analysis | +5 | Thoughtful analysis of target variable distribution with clinical connection |
| **Total** | 100 (+5 bonus) | |

---

## Hints (Read Before You Get Stuck!)

### ⚠️ Common Pitfalls:

1. **Values of 0 that aren't really zero**
   - Some columns (like `trestbps` and `chol`) have 0 values that represent missing data, not actual measurements
   - The `.isnull()` method won't detect these!
   - Always examine your data with `value_counts()` and check if extreme values make clinical sense

2. **Missing data varies by source**
   - The four medical centers have different data completeness
   - Some columns like `ca`, `thal`, and `slope` have extensive missing data
   - Understanding WHY data is missing is as important as knowing that it's missing

3. **The target variable has multiple levels**
   - `num` ranges from 0-4, not just 0-1
   - For many analyses, you'll want to convert this to binary (disease present/absent)

4. **Sex is coded as text**
   - Unlike some versions of this dataset, sex is "Male"/"Female" not 0/1

5. **Heart rate response calculation**
   - Remember to handle cases where thalch is missing or 0
   - The formula is (thalch / (220 - age)) * 100

### 💡 Pro Tips:

- Use `value_counts(dropna=False)` to see if there are any null values
- When something seems weird (like 0 blood pressure), investigate it—don't assume it's valid
- Cross-reference columns: do the patterns make clinical sense together?
- Read the original UCI documentation for additional context
- Always state what the data CAN tell you vs. what would require additional information

---

## Useful Resources

- **UCI Repository Page:** https://archive.ics.uci.edu/ml/datasets/heart+disease
- **Stress Test Interpretation:** https://www.mayoclinic.org/tests-procedures/stress-test/about/pac-20385234
- **Chronotropic Incompetence:** https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3188536/
- **Target Heart Rate Calculator:** https://www.heart.org/en/healthy-living/fitness/fitness-basics/target-heart-rates
- **Pandas Documentation:** https://pandas.pydata.org/docs/

---

*Remember: "Every Column Tells a Story" - your job is to figure out what that story is!*

---

**Due Date:** [See Canvas]

**Submission:** Upload your completed Jupyter notebook (.ipynb) to Canvas
