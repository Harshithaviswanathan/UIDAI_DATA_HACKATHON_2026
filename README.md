<div align="center">

<h1>📈 AadhaarSentinel</h1>
<h2>🧠 UIDAI DATA HACKATHON 2026</h2>
<h2>A National-Scale Study of Aadhaar Enrolment, Update, and Transition Patterns</h2>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.9+-brightgreen?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Google_Colab-Cloud-yellow?style=for-the-badge&logo=googlecolab&logoColor=black" alt="Colab"/>
  <img src="https://img.shields.io/badge/NumPy-Scientific-blue?style=for-the-badge&logo=numpy&logoColor=white" alt="NumPy"/>
  <img src="https://img.shields.io/badge/Pandas-Data_Analysis-blueviolet?style=for-the-badge&logo=pandas&logoColor=white" alt="Pandas"/>
  <img src="https://img.shields.io/badge/Seaborn-Stats_Viz-teal?style=for-the-badge" alt="Seaborn"/>
  <img src="https://img.shields.io/badge/Matplotlib-Plotting-success?style=for-the-badge" alt="Matplotlib"/>
  <img src="https://img.shields.io/badge/Scikit--Learn-ML-orange?style=for-the-badge&logo=scikit-learn&logoColor=white" alt="Scikit-learn"/>
</p>






</div>

<hr/>

<h2>❓ Problem Statement</h2>

<p>
Aadhaar is the backbone of India’s digital governance. However, as enrolment scales and
population mobility increases, UIDAI faces <b>three silent challenges</b> that are difficult
to detect using conventional dashboards:
</p>

<ul>
<li>Biometric update gaps that remain hidden until authentication failures occur</li>
<li>Migration-driven pressure that overloads specific districts and pincodes</li>
<li>Child-to-adult identity transitions that introduce systemic stress into Aadhaar infrastructure</li>
</ul>

<p>
These challenges do not appear as isolated failures. They emerge gradually, distributed
across geography, time, and age groups — making them <b>hard to detect early</b>.
</p>

<p>
<b>The core problem:</b> UIDAI data is rich, but lacks interpretable signals that
convert raw update counts into <i>actionable governance intelligence</i>.
</p>

<hr/>

<h2>💡 Our Solution</h2>

<p>
We propose a <b>multi-layer analytical framework</b> that transforms UIDAI enrolment and update
data into <b>early-warning indicators</b> for identity stress, migration pressure, and service gaps.
</p>

<p>
Instead of treating Aadhaar data as static records, our approach models it as a
<b>dynamic identity lifecycle system</b>.
</p>

<ul>
<li>We quantify <b>where</b> Aadhaar infrastructure is under stress</li>
<li>We identify <b>who</b> is being left behind in mandatory biometric updates</li>
<li>We detect <b>when</b> identity transitions intensify system pressure</li>
</ul>

<p>
The outcome is a set of <b>interpretable indices and risk scores</b> that UIDAI can directly
use for planning, auditing, and intervention.
</p>

<hr/>

<h2>🧠 Key Idea (Why This Is Different)</h2>

<p>
Most analyses focus on <i>volume</i>. We focus on <b>imbalance</b>.
</p>

<p>
An Aadhaar system under stress does not always show higher numbers — it shows
<b>disproportionate behavior</b> across age groups, regions, and update types.
</p>

<p>
Our framework captures these disproportions using carefully designed indices
that remain simple, explainable, and policy-friendly.
</p>

<hr/>

<h2>📊 Data Foundation</h2>

<table border="1" cellpadding="8" cellspacing="0">
<tr><th>Attribute</th><th>Value</th></tr>
<tr><td>Final Processed Records</td><td><b>4.26 Million</b></td></tr>
<tr><td>States / UTs</td><td><b>39</b></td></tr>
<tr><td>Districts</td><td><b>777</b></td></tr>
<tr><td>Pincodes</td><td><b>19,412</b></td></tr>
<tr><td>Time Period</td><td><b>March – December 2025</b></td></tr>
</table>

---

## 🗃️ Project Structure

```
├── 🗂️ data/                              
│   ├── enrolment.zip          #unzip 3 files and extract csv files           
│   ├── demographic.zip                      
│   └── biometric.zip                        
│
├── 🚀 uidai_solution.ipynb
│
├── 🎯 outputs/
│   └── graphs/                         
│   └── dashboards/
│
└── 📄 readme.md                         
```
---

## 🛠️ The 9-Step Data Engineering Pipeline
Our framework ensures 100% data integrity through a rigorous cleaning process.

<details>
<summary><b>View Pipeline Details</b></summary>

1. **Load & Concatenate**: Merging raw CSVs into unified DataFrames.
2. **Text Normalization**: Stripping whitespace, standardizing case, and special char removal.
3. **Invalid Row Filtering**: Removal of non-alphabetic geographic entries.
4. **Pincode Validation**: Regex-based 6-digit Indian Pincode verification.
5. **Negative Value Scrubbing**: Ensuring numeric consistency.
6. **Fuzzy District Consolidation**: Using `RapidFuzz` (90% threshold) to fix naming variants (e.g., *Ramanagara* → *Ramanagar*).
7. **Pincode Master Mapping**: Majority voting logic across datasets.
8. **Canonicalization**: Geographic standardization.
9. **Duplicate Removal**: Final exact-match cleanup.
</details>

---

## 🧠 Proprietary Indices & Mathematical Models

### 1. Trust Score Analysis
Identifies districts where Aadhaar activity deviates abnormally from population structures. It enables targeted audits instead of blanket reviews.
> **Formula:** $TrustScore = \frac{100}{1 + \log_{15}(PressureRatio)}$
* **Result:** Identified **98.3% of districts** as High-Risk with an average trust score of **17.8**.

### 2. Aadhaar Mobility Index (AMI)
Predicts the Life-Cycle of Mandatory Biometric Updates (MBU). Low AMI regions silently accumulate authentication risk.
* **Update Deserts:** Identified **99 pincodes** with critical biometric gaps.
* **At-Risk Children:** **4,902 children** flagged for missing mandatory age 5/15 updates.

### 3. Authentication Friction Risk (AFFR)
Detects the **"Paperwork Trap"**—where demographic updates create a false sense of compliance while biometrics remain stale.
* **Friction Score:** $demo\_updates / (bio\_updates + 1)$
* **Impact:** Predicts **40–60% higher authentication failure** at PDS/Banks in high-friction zones.

---

## 🤖 Machine Learning Performance

### **District Risk Classification**
Using a **RandomForestClassifier** to categorize district risk levels.

| Metric | Value |
| :--- | :--- |
| **Accuracy** | 99.36% |
| **Precision** | 99.67% |
| **F1-Score** | 92.69% |

**Feature Importance:** Total Update activity (20.2%) and Adult Population size (17.9%) are the strongest predictors of system stability.

---

## 🔍 Key Societal Insights
*   **The Adult Bias:** Adult updates are **64.7x** more frequent than child updates, revealing a critical policy gap in child biometric maintenance.
*   **Migration Pulse:** Identified **Pune, Thane, and Murshidabad** as the top 3 infrastructure pressure hubs due to high adult demographic shifts.
*   **Operational Failure:** Revealed systemic reprocessing issues in **Paschim Bardhaman**, with failure rates exceeding 17,000% of enrolment.

---

## 🎯 Impact for UIDAI

<ul>
<li>Early detection of biometric update deserts</li>
<li>Migration-aware infrastructure planning</li>
<li>Reduced authentication failures in welfare delivery</li>
<li>Focused audits instead of reactive troubleshooting</li>
</ul>

---

## 💡 Strategic Recommendations

<blockquote>
<b>Priority 1: Mobile Enrolment Van Deployment</b><br>
Immediate dispatch to the 99 "Update Deserts" identified by the AMI model to reach 4,902 at-risk children.
</blockquote>

<blockquote>
<b>Priority 2: Biometric Refresh Camps</b><br>
Targeting 15 high-friction districts (Score > 1.0) to prevent mass service denial at PDS shops.
</blockquote>

<blockquote>
<b>Priority 3: Infrastructure Scaling</b><br>
Capacity expansion in the Top 10 Migration Hubs to handle demographic update surges.
</blockquote>

---








