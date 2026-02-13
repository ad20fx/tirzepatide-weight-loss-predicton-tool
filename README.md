# **Weight Loss Prediction Calculator with Tirzepatide**

A web-based calculator that predicts personalized **weight loss trajectories over 72 weeks** for patients (adults above 18 years of age) using **Tirzepatide**, with interactive visualizations and interquartile range (IQR) confidence bands.

This tool is designed for educational and research purposes to explore expected weight-loss patterns under different patient profiles and dosing strategies. 


## 🎯 **Key Features**

1. Personalized Predictions: Calculates weight loss based on individual patient characteristics
   
2. Interactive Chart: Two interactive charts - Predicted body weight (kg) and Predicted total weight loss percentage

3. IQR Confidence Bands: Displays typical variation ranges based on typical variability observed in SURMOUNT-1 clinical trial data

4. Detailed Timeline: Week-by-week predictions at key timepoints (0, 4, 8, 12, 24, 36, 52, 72 weeks)

5. Real-time Updates: Instant calculations and graph generation

6. Responsive Design: Works seamlessly on desktop and mobile devices

   
## 📊 **What the Calculator Does**

This calculator estimates weight loss trajectories for adults prescribed Tirzepatide by considering:

1. Baseline anthropometrics: Current weight and height (BMI calculation)
   
2. Demographics: Age (adults only, ≥18 years) and Biological Sex
   
3. Tirzepatide dosage (5mg, 10mg, or 15mg)
   
4. Glycemic status (No Diabetes or Prediabetes) [⚠️ *Patients with Type 2 Diabetes are not supported in this model.*]

   
##   🧮 Prediction Model: Conceptual Approach ##


### Overview ###

The calculator uses an ***interpretable machine-learning framework*** with **SURMOUNT-1 clinical trial data** as its primary reference framework, for predicting long-term weight trajectories in a pharmacotherapy context. 

Specifically, the **longitudinal structure (72-week horizon)** and the **dose-dependent weight-loss magnitudes** are informed by the SURMOUNT-1 Phase 3 Trial, which evaluated Tirzepatide in adults with obesity or overweight without Type 2 Diabetes. 

Key features include 

(i) Using **LASSO Regression** to select a small set of clinically meaningful predictors: We use readily available baseline variables *Weight*, *Height*, *Age*, *Glycemic status* and *Treatment intensity (dose)* 

(ii) Applying **Classification and Regression Trees (CART)** for a *dose-level stratification*, *age-based adjustment*, *glycemic status differentiation (No Diabetes vs Prediabetes)*

(iii) Modeling **non-linear weight-loss trajectories** over time: This is done using a *logistic growth curve* capturing rapid early response and gradual plateau at later follow-up

(iv) Reporting outcomes with **median and IQR bands** to capture variability: The model reports *25th-75th percentile bands* representing typical variability across similar patients


### ✅ What this tool is ###

A *generalized* prediction calculator for adults who:

(i) Have obesity or overweight

(ii) Do not have type 2 diabetes

(iii) Are treated with Tirzepatide (5 mg, 10 mg, or 15 mg)


### ❌ What this tool is not ### 

(i) Not limited to SURMOUNT‑1 trial participants only or does not require that a user match SURMOUNT‑1 inclusion criteria exactly

(ii) Does not claim to reproduce individual patient outcomes from the trial

(iii) Not a patient‑specific clinical decision tool


### Model Assumptions, Thresholds, and Design CHoices ###

The goal is to achieve a transparent and interpretable modeling, rather than a black-box prediction game. 


#### How is Age handled ####

Post‑hoc analyses of SURMOUNT‑1 examined outcomes across age subgroups, commonly reported as: <50 years, 50 to 65 years, ≥65 years

Age is treated as a modifier, not a hard exclusion. A single interpretable threshold (~51 years) is used to distinguish Younger and Older adults, mirroring how decision-tree models (CART) identify age-based splits to simplify interpretation. 


#### Why these Specific Timepoints are used ####

Timepoints shown: Weeks 0, 4, 8, 12, 24, 36, 52, and 72

Rationale from SURMOUNT‑1: The trial measured weight repeatedly during three phases - Early titration phase, Post‑titration consolidation and Long‑term maintenance, thus demonstrating that Early response (e.g., Week 12) does not fully predict final outcome and many "slow responders" continue to lose weight through Week 72.


#### Dose Selection and Titration Assumptions ####

Typical Tirzepatide Doses include 5mg, 10mg and 15mg. But participants did not start at maintenance dose. The trial included an approximate *20-week titration period* starting at low dose and escalating gradually. The selected dose in the prediction calculator represents the intended maintenance dose. This implicity reflects gradual dose escalation thus avoiding overstating early weight loss while preserving accurate long-term efficacy. 


#### Why a Logistic (Non-linear) Time Curve is used ####

SURMOUNT-1 shows that weight loss accumulates gradually during titration and accelerates after dose stabilization with a plateau towars the end of follow-up. A *logistic curve captures this pattern better than a linear model by representing early adaptation, mid-phase acceleration and late-phase stabilization. 


#### Why Type 2 Diabetes is Explicitly Excluded ####

Weight-loss magnitude and mechanisms differ significantly in diabetes populations; separate clinical trials (such as SURMOUNT-2) address those groups. Thus including only "No Diabtees" and "Prediabetes" cases prevents extrapolation beyond the trial population. 


#### Inter-Quartile Range (IQR) Assumptions ####

The shaded band represents the 25th=75th percentile of expected outcomes, thus reflecting inter-individual variability as observed in SURMOUNT-1 cohort. It is *not a confidence interval* for an individual prediction. These are robust to outliers and have easier clinical interpretation. 


## 📈 Model Outputs ##

At each clinical timepoint, the tool provides:

1. Predicted body weight (kg)
   
2. Predicted BMI (kg/m²)

3. Predicted total weight loss (% from baseline)

4. IQR bounds (25th–75th percentile range)

5. A detailed tabular summary for all timepoints

   
## 🚀 **Getting Started**


### **Prerequisites:**

No installation required! This is a standalone HTML file that runs entirely in the browser.


### **Usage**

1. Download the HTML file or clone this repository

2. Open index.html in any modern web browser

3. Enter patient information:
   
   (i) Current weight (kg)

   (ii) Height (cm)

   (iii) Age (years, 18+)

   (iv) Biological Sex (Male/Female)

   (v) Select Tirzepatide dose (5mg, 10mg, or 15mg)

   (vi) Glycemic status (No Diabetes or Prediabetes)

4. Click **"Calculate Prediction"**


### **View results:**

Interactive graph with shaded IQR bands and a detailed prediction table at each clinical timepoint.


### 📈 **Interpretation**

#### **Weight Trajectory Chart:**

1. Solid Blue Line: Predicted body weight (kg) over time
   
2. Blue dashed lines: Upper and Lower IQR bounds

3. Blue Shaded region: Interquartile range (middle 50% of expected outcomes)

   
#### **Total Weight Loss Trajectory Chart:**

1. Solid Pink Line: Predicted cumulative Total weight loss (%)
   
2. Pink dashed lines: Upper and lower IQR bounds

3. Pink shaded region: Interquartile range
   

#### **Prediction Table:**

The table provides a numerical summary of the same predictions shown in the charts. Each row corresponds to a clinical timepoint (baseline or follow‑up week):

1. *Week*: The time since treatment initiation (in weeks).

2. *Weight (kg)*: The model‑predicted body weight at that timepoint.

3. *BMI (kg/m²)*: Calculated using predicted weight and baseline height.

4. *Weight Loss (%)*: Cumulative percentage total weight loss relative to baseline weight.

5. *IQR Range (kg)*: The expected 25th–75th percentile range for body weight at that timepoint. This reflects typical inter‑individual variability, not measurement error.
   

## ⚠️ **Important Disclaimers**

1. *Educational Purpose Only*: This tool is intended for research, demonstration, and educational purposes

2. *Not Medical Advice*: Should not replace clinical judgment or professional medical advice

3. *Not for Type 2 Diabetes*: This calculator is not intended for patients with Type 2 Diabetes

4. *Individual Results Vary*: Actual patient outcomes may differ significantly from modeled predictions

5. *Consult Healthcare Provider*: Always discuss treatment options with a qualified healthcare professional
   

## 🛠️ **Technical Details**


### **Technologies Used**

1. HTML5: Structure and content
   
2. CSS3: Styling with gradients and responsive grid layout

3. JavaScript: Calculation logic and interactivity

4. Chart.js: Interactive chart visualization library (CDN)

5. Browser Compatibility: Chrome 90+, Firefox 88+, Safari 14+, Edge 90+



