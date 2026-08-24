# 📉 Revenue Drop Investigation & Outage Impact Analysis

📊 [Click here to view the Executive Presentation (PDF)](#)  
💻 [View the Jupyter Notebook with Code & EDA](#)

## 📖 Business Context
In May 2024, the product experienced a sudden and significant drop in daily revenue. While a known technical outage occurred on May 16th, several other product updates were happening simultaneously, creating a "noisy" data environment. These concurrent events included:
* An active A/B split test
* A new OS release
* An email marketing logic update
* A reduction in the support team

**The Objective:** Conduct a deep-dive analysis to disentangle these overlapping events, understand the true root cause of the revenue degradation, and isolate the exact financial loss attributed *solely* to the technical glitch.

## 🎯 Key Questions Addressed
* What was the "net" financial loss directly caused by the outage versus the overall baseline revenue decline?
* Was the payment failure systemic, or localized to specific segments (e.g., OS version, traffic channel, Visa/Mastercard)?
* Did the ongoing A/B split test negatively impact the overall revenue trend?
* What other background factors contributed to the metric degradation?

## 🛠 Tools & Methodologies
* **Language:** Python
* **Libraries:** Pandas, Matplotlib, Seaborn
* **Core Competencies:** Product Analytics, Baseline Metrics Calculation, A/B Test Evaluation, Segment Analysis, Data Visualization, Root Cause Analysis (RCA).

## 📊 Key Metrics Analyzed
* **Monetization:** Daily Revenue, Average Revenue Per User (ARPU), Average Check
* **Technical Health:** Transaction Fail Rate, Success Rate
* **User Engagement:** Daily Active Users (DAU), New Paying Users

## 💡 Key Insights
The analysis revealed that the total revenue drop (~$15,900) was a compound effect of multiple factors, not just the technical outage:

* **🚨 Direct Outage Impact (52% of total loss):** The transaction Fail Rate spiked from 36.1% to 40.3% on May 16th. This systemic issue resulted in 1,933 "extra" failed transactions. The pure financial loss directly caused by the outage was calculated at **$9,070** over a 16-day period.
* **📉 Background Factors (43% of total loss):** Revenue was already degrading prior to the outage. This was driven by a downward trend in the dominant OS version (v2) and a nearly 50% drop in new paying users following a flawed email logic update in April.
* **✅ A/B Testing Verification:** The split test launched in March did *not* contribute to the drop. Group 1 showed a stable advantage (ARPU $3.14 vs. $2.76 in Group 0) with proper sample randomization.
* **🔍 Issue Localization:** The error rate increased evenly across all segments (OS versions, traffic channels, regions, and card types), ruling out third-party payment processor issues and confirming a systemic internal bug.

## 🚀 Actionable Recommendations
1. **Critical Priority:** Conduct a Root Cause Analysis (RCA) for the May 16th Fail Rate spike. Implement automated alerts for transaction Fail Rates exceeding the 37% threshold.
2. **High Priority:** Revert the April email logic changes, which severely disrupted user acquisition (dropped from ~1,800 to ~1,000 users/day). Set a strict KPI to restore new paying users to ≥1,400/day.
3. **Growth Opportunity:** Conclude the ongoing A/B test and roll out Group 1 settings to 100% of the audience. Based on the ARPU uplift, this has the potential to generate an additional ~$20K/month.

---
