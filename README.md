# 📊 Remote Work and Leisure Time: A Differences-in-Differences Analysis

## 🧠 Overview

This project investigates whether remote work during and after the COVID-19 pandemic led to an increase in leisure time for workers. Using **American Time Use Survey (ATUS)** data and a **Differences-in-Differences (DiD)** approach, we compare time-use trends for workers in remote-eligible jobs versus those in non-remote jobs before and after the pandemic.

---

## ❓ Research Question

> **Did remote work lead to an increase in leisure time for remote-eligible workers post-COVID?**  
We seek to understand if flexibility from remote work translated into more leisure or simply blurred the lines between work and personal life.

---

## 💡 Motivation

COVID-19 changed how we work. Remote work offered flexibility and eliminated commutes, but it's unclear whether that actually gave people more *leisure time*. This analysis helps answer that question using causal inference methods and real-world data.

---

## 📈 Methodology: Differences-in-Differences (DiD)

### 🔧 Formula (Algebraic Intuition)

(Treatment_post - Treatment_pre) - (Control_post - Control_pre) = DiD Estimate

### 📉 Model-Based Formula

```math
Y_{it} = \beta_0 + \beta_1 \cdot \text{Post}_t + \beta_2 \cdot \text{Treatment}_i + \beta_3 \cdot (\text{Post}_t \times \text{Treatment}_i) + \varepsilon_{it}
```

This allows us to control for confounders, get p-values, and interpret coefficients.

--- 

### 📌 Assumption: Parallel Trends
We assume that in the absence of the pandemic, both remote-eligible and non-remote workers would have followed similar time-use trends. Historical data from 2015–2019 is used to support this.

### 🧪 Hypotheses
Null Hypothesis (H₀): No differential change in work time between remote-eligible and non-remote workers post-pandemic (DiD = 0).

Alternative Hypothesis (H₁): Remote-eligible workers experienced a greater decrease in work time post-pandemic (DiD < 0), implying more leisure time.

### 📂 Data Overview
Data Source: American Time Use Survey (ATUS), 2015–2023

--- 

### Files Used
File	Purpose
Respondent	Demographics, labor force status, earnings
Activity Summary	Total time per activity (e.g., working, leisure) per respondent
Activity	Reclassify leisure time at a more granular level (start/end times, etc)

🔢 Variables Used
🧍 Demographics
TEAGE: Age
TESEX: Sex
PEEDUCA: Education level
PTDTRACE: Race
PEHSPNON: Hispanic origin

💼 Employment
TELFS.y: Labor force status
TEMJOT.y: Major job
TESPEMPNOT.y: Employer type
TRERNWA.y: Weekly earnings
TEERN: Hourly earnings
TRDPFTPT.y: Full-/Part-time status

⏰ Time Use
TTOT: Total time reported
TTHR: Total hours
TTWK: Time spent working
TRTALONE: Time spent alone
TRTFAMILY: Time with family

🗓️ Diary Metadata
TUDIARYDAY.y: Weekday/weekend indicator

📊 Analysis Goals
Conduct Exploratory Data Analysis (EDA)
Test for significance
Build a DiD model with covariates using backwards stepwise selection
Interpret treatment effects on leisure time

--- 
### 🧾 License
This project is for academic use only. Please cite appropriately if using this methodology or data.

### 🤝 Acknowledgments
ATUS (American Time Use Survey) data by the U.S. Bureau of Labor Statistics
SDSU Econometrics coursework for the theoretical framework
