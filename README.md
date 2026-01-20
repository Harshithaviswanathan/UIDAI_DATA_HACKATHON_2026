<div align="center">

<h1>📘 UIDAI DATA HACKATHON 2026</h1>
<h2>Unlocking Societal Trends in Aadhaar Enrolment & Update Dynamics</h2>

<p>
<b>Pan-India Analysis | 5.24M Enrolments | 103.85M Updates | 777 Districts | 19,412 Pincodes</b>
</p>

<img src="images/uidai_banner.png" alt="UIDAI Hackathon Banner" width="90%"/>

</div>

<hr/>

<h2>🧭 Executive Summary</h2>

<p>
This project presents a <b>nation-scale analytical framework</b> to understand Aadhaar enrolment,
update behavior, and identity lifecycle stress using UIDAI open data.
By transforming large-scale administrative records into interpretable indices,
the study enables <b>early risk detection, infrastructure planning, and policy-level decision support</b>.
</p>

<p>
The analysis processes <b>4.26 million high-integrity records</b> across
<b>39 States/UTs</b>, uncovering migration stress, biometric update gaps,
authentication friction, and child-to-adult identity transition vulnerabilities.
</p>

<hr/>

<h2>📊 Dataset Scale & Coverage</h2>

<table border="1" cellpadding="8" cellspacing="0">
<tr><th>Metric</th><th>Value</th></tr>
<tr><td>Total Enrolments</td><td><b>5.24 Million</b></td></tr>
<tr><td>Total Updates</td><td><b>103.85 Million</b></td></tr>
<tr><td>Final Processed Records</td><td><b>4.26 Million</b></td></tr>
<tr><td>States / UTs</td><td><b>39</b></td></tr>
<tr><td>Districts</td><td><b>777</b></td></tr>
<tr><td>Pincodes</td><td><b>19,412</b></td></tr>
<tr><td>Time Period</td><td><b>March – December 2025</b></td></tr>
</table>

<hr/>

<h2>🏗️ Analysis Architecture</h2>

<img src="images/architecture_pipeline.png" alt="Analysis Pipeline" width="85%"/>

<ol>
<li>Data Engineering & Canonicalization</li>
<li>Trust Score & Data Quality Risk Analysis</li>
<li>Aadhaar Mobility Index (AMI)</li>
<li>Authentication Friction & Failure Risk</li>
<li>Temporal Trends & System Maturity</li>
<li>Age-Group Dynamics</li>
<li>Migration Pulse & Infrastructure Stress</li>
<li>Machine Learning Risk Prediction</li>
</ol>

<hr/>

<h2>🔹 Module 1: Data Engineering Pipeline</h2>

<p>
A robust <b>9-stage cleaning and canonicalization pipeline</b> ensured the dataset
was suitable for national-scale analysis and policy use.
</p>

<ul>
<li>633,869 duplicate records removed</li>
<li>Zero invalid pincodes retained</li>
<li>777 standardized districts</li>
<li>19,412 validated pincodes</li>
</ul>

<img src="images/data_cleaning_flow.png" alt="Data Cleaning Flow" width="80%"/>

<hr/>

<h2>🔹 Module 2: Trust Score & Data Quality Risk</h2>

<p>
A policy-aware <b>Trust Score</b> was designed to identify districts with abnormal
Aadhaar update pressure relative to expected demographic behavior.
</p>

<pre>
expected_updates = 0.6 × age_5_17 + 0.2 × age_18_plus
pressure_ratio = total_updates / (expected_updates + 1)
trust_score = 100 / (1 + log₁₅(pressure_ratio))
</pre>

<p>
<b>Results:</b> Average Trust Score of <b>17.8</b>, with <b>98.3%</b> districts flagged as high risk.
</p>

<img src="images/trust_score_map.png" alt="Trust Score Heatmap" width="85%"/>

<hr/>

<h2>🔹 Module 3: Aadhaar Mobility Index (AMI)</h2>

<p>
AMI quantifies <b>mandatory biometric update compliance</b> at the pincode level,
revealing under-served and update-deficit regions.
</p>

<pre>
expected_bio_updates = (age_0_5 + age_5_17) × 0.40
AMI = actual_bio_updates / expected_bio_updates
</pre>

<ul>
<li>99 Update Deserts identified</li>
<li>4,902 children missing mandatory biometric updates</li>
<li>99.3% pincodes classified as healthy</li>
</ul>

<img src="images/ami_distribution.png" alt="AMI Distribution" width="80%"/>

<hr/>

<h2>🔹 Module 4: Authentication Friction Risk</h2>

<p>
Authentication Friction Score captures the imbalance between demographic and biometric updates,
indicating high likelihood of authentication failure.
</p>

<pre>
friction_score = demographic_updates / (biometric_updates + 1)
</pre>

<p>
Districts with extreme friction show <b>40–60% higher authentication failure probability</b>.
</p>

<img src="images/friction_hotspots.png" alt="Authentication Friction Hotspots" width="85%"/>

<hr/>

<h2>🔹 Module 5: Temporal Trends & System Maturity</h2>

<p>
Time-series analysis reveals Aadhaar’s evolution from mass enrolment to a
<b>stable maintenance-driven ecosystem</b>.
</p>

<ul>
<li>Trust Score improved by <b>+2.26 points</b></li>
<li>Reduced volatility over time</li>
</ul>

<img src="images/temporal_trends.png" alt="Temporal Trends" width="80%"/>

<hr/>

<h2>🔹 Module 6: Age-Group Dynamics</h2>

<p>
Adult Aadhaar interaction intensity is <b>64.7× higher</b> than that of children,
revealing severe child biometric stagnation risk.
</p>

<img src="images/age_group_distribution.png" alt="Age Group Analysis" width="75%"/>

<hr/>

<h2>🔹 Module 7: Migration Pulse & Infrastructure Stress</h2>

<p>
Migration is inferred using adult demographic updates, identifying high-pressure urban hubs.
</p>

<ul>
<li>Pune – 302,115</li>
<li>Thane – 265,348</li>
<li>Murshidabad – 241,305</li>
<li>Surat – 231,926</li>
<li>Bengaluru – 222,700</li>
</ul>

<img src="images/migration_map.png" alt="Migration Stress Map" width="85%"/>

<hr/>

<h2>🔹 Module 8: Machine Learning Models</h2>

<p>
Machine learning enables automated prioritization of districts and pincodes.
</p>

<ul>
<li><b>Random Forest Classifier:</b> 99.36% accuracy</li>
<li><b>Random Forest Regressor:</b> MAE = 0.3787</li>
</ul>

<img src="images/ml_results.png" alt="ML Results" width="80%"/>

<hr/>

<h2>🎯 Strategic Recommendations</h2>

<ul>
<li>Deploy mobile biometric vans in update deserts</li>
<li>Audit high-risk districts flagged by Trust Score</li>
<li>Target migration hubs for infrastructure scaling</li>
</ul>

<hr/>

<h2>📌 Conclusion</h2>

<p>
This project demonstrates how UIDAI data, when rigorously cleaned and analytically modeled,
can support <b>predictive, preventive, and inclusive governance</b> at national scale.
</p>

<hr/>

<h3>📂 Repository Contents</h3>

<ul>
<li><code>UIDAI_Complete_ML.ipynb</code></li>
<li><code>Data_Cleaning_Pipeline.ipynb</code></li>
<li><code>ML_Models.ipynb</code></li>
<li><code>UIDAI_Hackathon_Presentation.pdf</code></li>
</ul>

<div align="center">
<b>UIDAI Data Hackathon 2026 | Team Submission</b>
</div>
