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

### 4. Temporal Analysis
* The temporal analysis models Aadhaar’s lifecycle using enrolments as identity inflow, update activity as maintenance load, and a derived Trust Score to quantify database stability over time.
* An increasing Trust Score trend (≈0.1 → 2.3) indicates a gradual transition from mass enrolment toward a more stable, service-sustainability phase.
* Monthly monitoring enables early detection of policy-induced update surges, supporting proactive capacity planning and system resilience.

### 5. Age-Based Identity Transition Analysis
* Analyzes biometric update compliance across children, adults, and seniors
* Identifies critical gaps in mandatory Age 5 & Age 15 biometric updates
* Reveals a severe adult-update bias — adult updates are 64.7× higher than child updates
* Flags 4,902 children at high risk of future authentication failure

---
![AMU DASHBOARD IMG](./outputs/dashboards/3.png)


## 🤖 Machine Learning Performance

<p> Beyond descriptive analytics, AadhaarSentinel uses supervised machine learning to <b>predict future risk patterns</b> in Aadhaar infrastructure — enabling UIDAI to act <b>before failures occur</b>. </p> <hr/>
🧠 District Risk Classification (System Stress Prediction)
<p> This model classifies districts into <b>Low, Medium, and High Risk</b> categories based on enrolment pressure, update imbalance, demographic structure, and migration signals. </p> <ul> <li><b>Objective:</b> Identify districts likely to experience authentication failures or service overload</li> <li><b>Algorithm:</b> Random Forest Classifier</li> <li><b>Key Inputs:</b> Enrolments, biometric updates, demographic updates, adult population share</li> <li><b>Policy Use:</b> Enables <b>targeted audits</b> instead of blanket inspections</li> </ul> <table> <tr><th>Metric</th><th>Value</th></tr> <tr><td>Accuracy</td><td><b>99.36%</b></td></tr> <tr><td>Precision</td><td><b>99.67%</b></td></tr> <tr><td>F1-Score</td><td><b>92.69%</b></td></tr> </table> <p> <b>Top Predictors:</b> Total update volume (20.2%) and adult population size (17.9%) </p> <hr/>
🧠 Biometric Update Desert Prediction (Future Failure Zones)
<p> This model predicts <b>pincodes likely to become biometric update deserts</b>, where mandatory updates are chronically missed despite active demographic changes. </p> <ul> <li><b>Objective:</b> Predict silent biometric neglect before authentication failures spike</li> <li><b>Learning Signal:</b> Low bio-updates + high demographic churn</li> <li><b>Output:</b> Binary risk flag for each pincode</li> <li><b>Policy Use:</b> Guides <b>mobile enrolment van deployment</b></li> </ul> <p> <b>Prediction Outcome:</b> Identified <b>99 high-risk pincodes</b> likely to face future authentication failures without intervention. </p> <hr/>
🧠 Child Identity Transition Risk Prediction
<p> This model predicts <b>children at risk of Aadhaar identity failure</b> due to missing mandatory biometric updates at age 5 and 15. </p> <ul> <li><b>Objective:</b> Detect identity transition failures before adulthood</li> <li><b>Key Features:</b> Age cohort, biometric history, district-level update behavior</li> <li><b>Risk Signal:</b> Age threshold crossed without biometric refresh</li> <li><b>Policy Use:</b> Prevents long-term exclusion from welfare and education services</li> </ul> <p> <b>Prediction Outcome:</b> Flagged <b>4,902 children</b> as high-risk for future authentication failure. </p> <hr/>

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








