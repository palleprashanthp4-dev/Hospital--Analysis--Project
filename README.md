<p align="center">

<table>
<tr>
<td bgcolor="black" align="center">

<font color="white"><i><b>🏥 Hospital Data Dashboard — README</b></i></font>

</td>
</tr>
</table>

</p>
 <p>
A multi-page analytical dashboard built across three views: 
<mark style="background-color:pink;">Overview</mark>, 
<mark style="background-color:pink;">Clinical Deep-Dive</mark>, and 
<mark style="background-color:pink;">Predictive Analytics &amp; Forecasts</mark>. 
Together they tell the full story of 984 patients across diseases, demographics, costs, and future projections.
</p>
---

## 📸 Dashboard Screenshots

### Dashboard 1 — Overview
![Overview Dashboard](https://github.com/palleprashanthp4-dev/Hospital--Analysis--Project/blob/main/output-img/hospital_page1_overview.png)

### Dashboard 2 — Clinical Deep-Dive
![Clinical Deep-Dive](https://github.com/palleprashanthp4-dev/Hospital--Analysis--Project/blob/main/output-img/hospital_page2_clinical.png)

### Dashboard 3 — Predictive Analytics & Forecasts
![Predictive Analytics](https://github.com/palleprashanthp4-dev/Hospital--Analysis--Project/blob/main/output-img/hospital_page3_predictions.png)

---

## 📊 Dashboard 1: Overview

### 🔢 Key KPIs

| Metric                  | Value     |
|-------------------------|-----------|
| Total Patients          | 984       |
| Readmission Rate        | 26.8%     |
| Avg Treatment Cost      | $8,367    |
| Avg Length of Stay      | 37.7 days |

### 🔍 What's Happening

- **Gender Split:** The patient population skews slightly female (53.3% vs 46.7% male), indicating broader female healthcare utilisation or higher vulnerability in this cohort.
- **Most Common Diseases:** Fractured Leg and Heart Attack are the top diagnoses (67 patients each), followed closely by 14 other conditions each ranging between 64–66 patients — a remarkably even disease spread suggesting a general-purpose hospital.
- **Patient Outcomes:** 60.1% of patients recovered fully, while 39.9% were discharged as "Stable" — no critical/deceased outcome category visible, which is a strong overall outcome signal.
- **Patient Satisfaction:** Allergic Reaction and Fractured Arm patients gave the highest satisfaction scores (5.0/5), while Stroke patients rated satisfaction the lowest (2.0/5), likely reflecting treatment complexity and recovery difficulty.
- **Age Distribution:** The mean patient age is **53.8 years**, with the largest patient cluster in the 50–60 age band — a middle-aged to elderly cohort consistent with the disease profile.

---

## 🔬 Dashboard 2: Clinical Deep-Dive

### 🔍 What's Happening

#### Disease Distribution by Gender (Q3)
- Disease burden is **nearly equal between male and female** patients across all 15 conditions (all bars approximately 65–67 patients per gender per disease).
- No disease shows a significant gender skew — this either reflects a well-balanced population or data normalisation.

#### Average Treatment Cost per Disease (Q4)
| Disease              | Avg Cost   |
|----------------------|------------|
| Cancer               | $25,000    |
| Prostate Cancer      | $20,000    |
| Heart Attack         | $18,000    |
| Heart Disease        | $15,000    |
| Childbirth           | $12,000    |
| Stroke               | $10,000    |
| Appendicitis         | $8,000     |
| Kidney Stones        | $6,000     |
| Osteoarthritis       | $4,000     |
| Fractured Leg        | $3,000     |
| Diabetes             | $2,000     |
| Hypertension         | $1,000     |
| Respiratory Infection| $800       |
| Fractured Arm        | $500       |
| Allergic Reaction    | $100       |

- **Cancer is 250× more expensive than an Allergic Reaction**, highlighting extreme cost variance within the same hospital.
- The **top 5 diseases (Cancer, Prostate Cancer, Heart Attack, Heart Disease, Childbirth) account for ~72% of total treatment costs**, despite each condition representing only ~65–67 patients.

#### Total Cost Share (Q4 — Pie)
- **Cancer + Prostate Cancer alone account for ~40.2%** of total hospital costs — a major cost concentration risk.
- Heart Attack (14.6%) and Heart Disease (11.8%) add another ~26.4%.
- All other conditions share just ~33.4% of costs.

#### Avg Length of Hospital Stay per Disease (Q7)
- **Cancer patients stay the longest** (42.7 days), followed by Prostate Cancer (41.6d) and Heart Attack (41.0d).
- **Allergic Reaction has the shortest stay** (34.2 days) — still relatively long, suggesting these are inpatient metrics.
- All stays are coded by intensity: 🔴 >45 days (High), 🟠 35–45 days (Medium), 🟢 <35 days (Low).

#### Readmissions by Disease (Q10)
- **Heart Attack dominates readmissions (67)**, followed by Heart Disease (64), and a cluster of diseases at 33 (Appendicitis, Fractured Arm, Cancer, Stroke, Diabetes).
- Heart conditions are the **primary readmission risk** and deserve targeted post-discharge care protocols.

---

## 🤖 Dashboard 3: Predictive Analytics & Forecasts

### 🔍 What's Happening

#### PRED 1 — Avg Treatment Cost by Age Group (with Forecast)
- Treatment costs **rise sharply with age**: from $3,175 for ages 25–34 up to $11,332 for ages 55–64.
- There's a dip at 65–74 ($9,431) — possibly reflecting Medicare coverage effects — before the **forecast jumps to $13,123+ for ages 75–84 and beyond**.
- Linear regression projects costs will continue climbing as the patient population ages, representing a significant financial planning challenge.

#### PRED 2 — Readmission Risk % per Disease
| Disease               | Readmission Risk |
|-----------------------|-----------------|
| Heart Attack          | **100%**        |
| Heart Disease         | **98.5%**       |
| Appendicitis          | 50%             |
| Cancer                | 50%             |
| Stroke                | 50%             |
| Fractured Arm         | 50%             |
| Diabetes              | 1.5%            |
| All others            | 0.0%            |

- **Heart Attack and Heart Disease are near-certain readmission risks** — every such patient is expected to return. This demands aggressive discharge planning and follow-up protocols.
- The 50% threshold (dashed line) cleanly separates high-risk from low-risk diseases — useful for triage prioritisation.

#### PRED 3 — Cost vs Length of Stay Regression
- There is a **positive correlation between length of stay and treatment cost** (R² shown, slope is statistically significant at p<0.01).
- **Predicted cost at 80 days = $10,283** — the regression forecasts that extremely long stays push costs past $10K regardless of disease.
- The scatter shows wide variance, meaning other factors (disease type, intervention) heavily modulate cost beyond just days stayed.

#### Satisfaction by Gender & Disease
- Satisfaction scores differ between male and female patients depending on disease — **females report higher satisfaction for several conditions** (e.g., Allergic Reaction: female = 5.0 vs male = 3.5).
- Stroke is a consistent low-satisfaction outlier for both genders, suggesting systemic issues with stroke patient care experience.

#### PRED 5 — Cost Heatmap (Disease × Outcome)
- Most diseases show costs aligned with either **"Recovered"** or **"Stable"** outcomes, but rarely both — indicating that patient trajectory is disease-specific.
- Cancer ($25K), Prostate Cancer ($20K), Heart Attack ($18K) costs are exclusively tied to the "Stable" outcome — suggesting these expensive cases rarely reach full recovery.
- Low-cost diseases (Allergic Reaction $100, Fractured Arm $500) are tied to "Recovered" — quick, inexpensive, and complete recovery.

#### PRED 6 — Monthly Admission Forecast
- Historical admissions fluctuated significantly (range ~70–93 patients/month).
- The **6-month forecast stabilises at ~84 patients/month** with a relatively narrow confidence interval (shaded band = 95% CI).
- This suggests **no expected surge or decline** — hospital capacity planning can assume steady-state operations for the near term.

---

## 🧠 Key Conclusions

| Theme                     | Insight |
|---------------------------|---------|
| 💰 **Cost Concentration** | Cancer & Prostate Cancer consume ~40% of all treatment costs despite representing ~13% of patients |
| ❤️ **Readmission Crisis** | Heart Attack (100%) and Heart Disease (98.5%) are near-guaranteed readmissions — intervention is critical |
| 📈 **Aging Cost Pressure** | Treatment costs will rise sharply for patients aged 75+ — financial modelling must account for this |
| 😊 **Satisfaction Gap**   | Stroke patients rate satisfaction at 2.0/5 — a systemic care quality gap needing urgent attention |
| 🛏️ **Long Stays = Oncology** | Cancer patients stay ~42.7 days on average, the longest of all conditions |
| ⚖️ **Gender Equity**       | Disease burden and costs are near-equally distributed between male and female patients |
| 📅 **Stable Demand**       | Admission forecast is steady at ~84/month — no operational surge expected in next 6 months |

---

## 🛠️ Technical Notes

- All charts rendered in a dark-theme dashboard layout.
- Statistical methods used: linear regression (cost forecasting), confidence intervals (admission forecast), R² correlation analysis (cost vs LOS).
- Predictive models flag age groups 75–84 and 85+ as extrapolated (marked with `*`).

---

*Dashboard generated from hospital patient records (n=984). All values represent patient-level aggregates.*
