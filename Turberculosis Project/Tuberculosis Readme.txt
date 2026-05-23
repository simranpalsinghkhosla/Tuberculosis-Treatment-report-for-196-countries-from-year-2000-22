# Historical Tuberculosis Treatment Success Rate Analysis (2000–2022)

## 📌 Project Overview
This project analyzes global Tuberculosis (TB) treatment success rates for new and relapse cases over two decades (2000–2022). Using Python, the pipeline handles data cleaning, handles data types, and applies inferential statistical modeling to uncover public health trends.

---

## 📊 About the Dataset
* **Source:** Global monitoring data spanning 217 countries/regions.
* **Temporal Range:** Main focus from 2000 to 2022.
* **Features:**
  * `Entity`: Country or geographic region.
  * `Code`: Standard 3-letter country code.
  * `Year`: Reporting year.
  * `New and relapse cases`: Treatment success rate percentage (%).

---

## 🛠️ Model & Methodology

### Data Preprocessing
* Removed missing values from the target success rate feature.
* Handled explicit row duplicates to ensure data integrity.
* Converted features to appropriate data types (`int` for Year, `float` for Success Rate).
* Isolated the **2022 reporting year** data for a focused cross-sectional analysis.

### Statistical Model Used
* **Model:** **Student's t-Distribution** (`scipy.stats.t.interval`).
* **Why it was used:** Ideal for calculating confidence intervals when estimating parameters from sample indicators rather than the entire population.
* **Confidence Level:** 95% Confidence Interval (CI).
* **Metrics calculated:** Sample Size, Sample Mean , Standard Deviation, and Sample Standard Error.

---

## 📈 Key Inferences & Findings

* **Wide Disparities:** Country-level success rates showed massive global variations, ranging from near **0%** in underperforming regions up to an absolute **100%** (e.g., Andorra hitting 100% in 2022).
* **Regional Discrepancies:** Key developing regions showed high tracking efficiency (e.g., Afghanistan registering a **95%** success rate metric), while others face infrastructure bottlenecks.
* **The 95% Confidence Boundary:** The calculated t-interval bounds a precise global average window. This proves that while individual countries vary heavily, global public health efforts have converged tightly around a consistent, successful baseline over time.

---

## 💻 Tech Stack
* **Language:** Python
* **Libraries:** `pandas`, `numpy`, `scipy` (Statistics), `matplotlib`, `seaborn` (Visualization)