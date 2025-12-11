# From Data to Revenue: Leveraging A/B Testing to Enhance Conversion and Engagement

## Project Overview
This project is my hands-on exploration of A/B testing in the real world. I simulated, analyzed, and validated an experiment to understand how a redesigned website feature affects user behavior. The goal was simple: see if changes to the product can actually drive higher conversions and better engagement.  

I built this project not just to practice data science, but to demonstrate that data-driven decisions can translate directly into business value.

**[READ THE FULL REPORT (PDF)](/Report.pdf)**
---

## Objectives
- **Measure the impact of a new feature:** Determine if the redesigned website feature improves user conversion rates.  
- **Understand user behavior:** Identify which segments of users benefit most from changes.  
- **Validate results statistically:** Apply rigorous methods to ensure improvements aren’t just random chance.  
- **Enable future experiments:** Provide a roadmap for efficient A/B testing and decision-making.

---

## Table of Contents
- [From Data to Revenue: Leveraging A/B Testing to Enhance Conversion and Engagement](#from-data-to-revenue-leveraging-ab-testing-to-enhance-conversion-and-engagement)
  - [Project Overview](#project-overview)
  - [Objectives](#objectives)
  - [Table of Contents](#table-of-contents)
  - [Business Problem: Why This Matters](#business-problem-why-this-matters)
  - [Tech Stack](#tech-stack)
  - [Data Preparation \& Feature Engineering](#data-preparation--feature-engineering)
  - [Statistical Methods Comparisons](#statistical-methods-comparisons)
  - [Key Business Insights](#key-business-insights)
  - [Project Capabilities](#project-capabilities)
  - [Real-World Impact](#real-world-impact)
  - [How to Run the Project](#how-to-run-the-project)
  - [Author: Hannan Baig](#author-hannan-baig)

---

## Business Problem: Why This Matters
Every digital business faces the same challenge: how to convert users into loyal customers. Even small improvements in conversion rates can translate into thousands of additional purchases or sign-ups.  

This project demonstrates a practical framework for testing changes in a product or website feature and quantifying their real business value. It shows that **data science isn’t just about models or numbers—it’s about making better decisions that drive measurable results**.

---

## Tech Stack

| Category | Technology | Primary Usage in Code/Purpose |
| :--- | :--- | :--- |
| **Data Manipulation & Core Scientific** | `pandas` (`pd`) | Core library for creating the mock data `DataFrame`, loading the CSV, performing EDA, data cleaning, grouping, pivoting, and aggregation. |
| **Data Manipulation & Core Scientific** | `NumPy` (`np`) | Used for efficient numerical operations, especially for generating random data (e.g., binomial distributions for conversions, random integers for clicks/views) and array concatenation. |
| **Date/Time** | `datetime`/`timedelta` | Used for generating realistic timestamps (`Date` column) for the mock A/B test data, spanning the 14-day duration. |
| **Statistics & A/B Testing** | `statsmodels.stats.proportion` | **Crucial for A/B testing:** Functions like `proportions_ztest` (to determine significance) and `confint_proportions_2indep` (to calculate the confidence interval for the lift). |
| **Statistics & A/B Testing** | `statsmodels.stats.power` | Used for power analysis to calculate the required sample size and the retrospective power of the completed test based on the observed effect size. |
| **Visualization** | `matplotlib.pyplot` (`plt/plot`) | Core library for plotting the time-series analysis of daily conversion rates, including the confidence intervals. |
| **Statistics** | `scipy.stats` | Used to perform the t-test (`ttest_ind`) to check for statistical differences in the engagement metric (`Clicks`) between the two groups. |



---

## Data Preparation & Feature Engineering
- **Simulated Dataset:** Created 10,000 unique user records across Control (original) and Treatment (new) groups.  
- **Metrics Generated:** Conversion status, clicks, page views, dates.  
- **Data Validation:** Ensured no duplicate users, correct date formats, clicks ≤ page views, and proper group randomization.  
- **Feature Engineering:**  
  - Engagement segmentation using median clicks (high vs. low engagement)  
  - Daily conversion rate calculation  
  - Aggregated engagement metrics for statistical analysis  

*The focus was on building a dataset that mimics real-world behavior while maintaining integrity for valid analysis.*

---

## Statistical Methods Comparisons
Although this is primarily an A/B testing project, I applied multiple statistical methods to validate findings:

| Method | Purpose | Pros | Cons |
|--------|--------|------|------|
| **Z-Test (Proportions)** | Compare conversion rates between groups | Simple, widely used, highly interpretable | Assumes large sample size |
| **Time-Series Analysis** | Observe daily performance trends | Captures temporal dynamics | Descriptive only |
| **Segmentation Analysis** | Identify high-value users | Provides actionable insights | Requires clear feature selection |
| **T-Test (Clicks)** | Validate secondary engagement metric | Confirms overall UX improvement | Assumes approximate normality for means |

**Final Choice:** All methods were complementary. Z-test confirmed primary conversion lift, t-test verified engagement, and segmentation analysis pinpointed high-value users. This multi-method approach ensures robust, real-world conclusions.


![Confidence Interval Bands](Images/Confidence_Interval_Bands.png)
***Figure: Conversion Rate Analysis for Control vs. Treatment Group (with 95% Confidence Intervals). The Treatment group consistently performs better.***
---

## Key Business Insights
- **Overall Conversion Lift:** Treatment group showed a 2.22% absolute increase (23.17% relative lift) in conversions.  
- **High-Value Users:** Most engaged users saw a 2.84% lift (30.9% relative) in conversions—proof that targeted design changes yield significant results.  
- **Low-Engagement Users:** Also benefited, with a 1.62% lift (16.3% relative).  
- **Daily Performance Stability:** Treatment consistently outperformed Control over 14 days, confirming reliable uplift.  
- **Secondary Engagement:** Treatment users clicked more (avg. 8.07 vs. 6.93), signaling improved UX.  

*These insights are actionable, informing marketing strategy, product improvements, and future experiment design.*

---

## Project Capabilities
This project demonstrates the ability to:  
- Simulate realistic A/B testing datasets  
- Conduct thorough data quality checks and validation  
- Perform statistical testing for primary and secondary metrics  
- Conduct time-series and segment analyses for deeper understanding  
- Estimate statistical power and required sample size for future tests  
- Provide direct business impact calculations (extra conversions per 10k users)  

*It’s adaptable to different features, products, and industries.*

---

## Real-World Impact
- For every 10,000 users exposed to the new feature: +222 conversions  
- Scales to 100,000 monthly visitors: +2,220 conversions  
- Provides a **data-driven roadmap for improving revenue, engagement, and UX**  
- Supports faster, more efficient future experiments with calculated sample sizes  

*This project proves that even small, data-informed changes can have a measurable business impact.*

---

## How to Run the Project
1. **Clone the repository**:  
   ```bash
   git clone https://github.com/hannanbaig347/from-data-to-revenue-leveraging-AB-testing-to-enhance-conversion-and-engagement.git


2.  **Navigate into the folder:**

    ```bash
    cd Notebooks
    ```

3.  **Install dependencies** (preferably in a virtual environment):

    ```bash
    pip install -r requirements.txt
    ```

4.  **Open the notebook:**
    Open `Leveraging_AB_Testing_To_Enhance_Conversion_And_Engagement.ipynb` in **Jupyter Notebook**.

5.  **Run each cell step-by-step to replicate:**

      * Dataset simulation
      * Data validation & cleaning
      * Statistical testing (Z-test, T-test)
      * Time-series visualization
      * Segment analysis
      * Statistical power and future planning

> **Note:** All plots, tables, and outputs are generated automatically.

-----

## Author: Hannan Baig

I’m **Hannan Baig**, an aspiring Data Scientist, learning by doing and striving to make an impact. This project represents not just a technical exercise, but a personal mission: to demonstrate that data-driven decisions can improve real business outcomes.

I’m passionate about translating raw data into actionable insights, and every project I create is a step toward building measurable value in the real world.

If you find this project interesting or useful, feel free to star ⭐ the repo\! Feedback and collaboration are always welcome.

**Contact**

- Email: `muhammadhannanbaig@gmail.com`
- GitHub: `github.com/hannanbaig347`
- LinkedIn: [`Hannan Baig`](https://www.linkedin.com/in/hannan-baig-b10320325/)

-----



