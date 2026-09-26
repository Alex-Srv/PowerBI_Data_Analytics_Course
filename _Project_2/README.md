# Data Job Market Analysis: Remote vs. On-Site Dynamics (Power BI)

📂 **Project File:** [Download my project 2.pbix](my%20project%202.pbix)

![Dashboard Overview](Dashboard_Preview.png)

An interactive Microsoft Power BI analytical dashboard engineered to examine the data career landscape (Data Science, Data Analytics, Data Engineering) with a focus on work flexibility. The project assesses how workplace format (**Remote / Work From Home** vs. **On-Site**) affects compensation benchmarks, global geographic distribution, technology stack demand, and recruitment seasonality throughout the calendar year.

---

## 📌 Project Objectives

* Compare median compensation structures across fixed annual salaries and hourly rate equivalents by specialization and country.
* Provide a flexible multi-dimensional (Ad-hoc) exploration layer featuring dynamic analytical axes and metric parameter switches.
* Assess hiring volume trends and cyclical recruitment behavior throughout the year broken down by job role and work format.

---

## 🛠 Tech Stack & Architecture

* **Power BI Desktop**: UI/UX layer, component layering via Selection Panel, Button Slicers, and Cross-page Slicer Synchronization.
* **Power Query (M)**: Data transformation pipelines, date type standardization to prevent timestamp grain mismatches, null value cleansing, and categorical work type flag generation (`Work type`).
* **DAX**: Modeling of custom metrics (`Job count`, `Median salary yearly`, `Median salary year/ hourly`) and Field Parameters integration.
* **Data Modeling**: Star schema connecting the central fact table (`job_postings_fact`) to dimensions (`Calendar`, `company_dim`, `skills_dim`, `skills_job_dim`) with active relationship handling.

---

## 📊 Report Structure & Slide Breakdown

### Page 1: Yearly vs. Hourly Salary Dynamics
* **Focus**: Evaluation of remuneration methods across roles and worldwide geographic distribution.
* **Core Visuals**:
  * **Clustered Bar Chart**: Side-by-side comparison of `Median salary yearly` and `Median salary year/ hourly` across data job titles.
  * **Map**: Global geographic representation of job demand density by country.
* **Filters**: Work arrangement toggle (`Work From home` vs. `Work on site`) and role selection.

### Page 2: Ad-Hoc Parameter Explorer (One for All)
* **Focus**: Flexible, full-scope data discovery without restrictive top-N truncations, allowing detailed inspection of the entire technology ecosystem.
* **Core Visuals**:
  * **Dynamic Bar Chart**: Visualization driven by DAX Field Parameters.
  * **Field Parameters Interface**:
    * **Category Axis (Dimension)**: Dynamic switching between `Job Title Name`, `Job Country`, `Skills`, and `Company name`.
    * **Measure Selection (Metric)**: Instant recalculation across `Job count`, `Median salary year/ hourly`, and `Median salary yearly`.
* **Highlights**: Allows end users to investigate niche tools and specific salary distributions across remote and on-site roles without modifying underlying report views.

### Page 3: Hiring Trends & Seasonality (Hire Rating)
* **Focus**: Longitudinal volume behavior of data job postings across the calendar year.
* **Core Visuals**:
  * **Line Chart**: Continuous hiring trajectory showing monthly open job volumes (`Job count`).
  * **Direct Data Labels**: Prominent data points highlighting hiring activity surges (spring peak) and seasonal contractions (late Q4).
* **Highlights**: Date granularity resolved via a dedicated date dimension table (`Calendar`) properly joined to job posting timestamps.

---

## 💡 Key Analytical Findings

1. **Work Format & Pay**: Remote-eligible roles demonstrate competitive median compensation rates relative to on-site equivalents, while drawing from a broader, internationally distributed employer pool.
2. **Hiring Seasonality**: Job posting volumes follow distinct annual patterns, peaking strongly during the spring recruitment wave (March–May) before tapering off toward late autumn.
3. **Skill Valuation**: Advanced data infrastructure technologies and cloud platforms command superior median hourly and annual compensation compared to foundational operational toolsets.