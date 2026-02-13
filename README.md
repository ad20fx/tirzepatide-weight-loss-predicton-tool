# **Weight Loss Prediction Calculator with Tirzepatide**

A web-based calculator that predicts personalized **weight loss trajectories over 72 weeks** for patients (adults above 18 years of age) using **Tirzepatide**, with interactive visualizations and interquartile range (IQR) confidence bands.

This tool is designed for educational and research purposes to explore expected weight-loss patterns under different patient profiles and dosing strategies. 

## 🎯 **Key Features**

1. Personalized Predictions: Calculates weight loss based on individual patient characteristics
   
2. Interactive Chart: Two interactive charts - Predicted body weight (kg) and Predicted total weight loss percentage

3. IQR Confidence Bands: Displays typical variation ranges based on typical variability observed in SURMOUNT-1 clinical trial data

4. Detailed Timeline: Week-by-week predictions at key timepoints (0, 4, 8, 12, 24, 36, 52, 72 weeks)

5. Responsive Design: Works seamlessly on desktop and mobile devices

6. Real-time Updates: Instant calculations and graph generation

   
## 📊 **What the Calculator Does**

This calculator estimates weight loss trajectories for adults prescribed Tirzepatide by considering:

1. Baseline anthropometrics: Current weight and height (BMI calculation)
   
2. Demographics: Age (adults only, ≥18 years) and Biological Sex
   
3. Tirzepatide dosage (5mg, 10mg, or 15mg)
   
4. Glycemic status (No Diabetes or Prediabetes) [⚠️ *Patients with Type 2 Diabetes are not supported in this model.*]

   
##   🧮 Modeling Approach ##

The prediction engine combines:

1. Dose‑specific baseline efficacy derived from SURMOUNT-1 clinical trial data
   
2. CART‑style stratification, including:
 
 (i) Age threshold adjustment (>51 years)
 
 (ii) BMI‑based scaling

 (iii) Glycemic status stratification (No Diabetes vs Prediabetes)


***Logistic growth curve*** to model realistic weight‑loss dynamics over time with IQR bands to represent typical inter‑individual variability


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

   
#### **Total Weight Trajectory Chart**

1. Solid Pink Line: Predicted cumulative Total weight loss (%)
   
2. Pink dashed lines: Upper and lower IQR bounds

3. Pink shaded region: Interquartile range


(i) Timepoint: Baseline or week number

(ii) Weight (kg): Predicted body weight

(iii) BMI (kg/m²): Body Mass Index

(iv) Weight Loss (%): Cumulative percentage weight loss from baseline

## ⚠️ **Important Disclaimers**

*Educational Purpose Only*: This tool is intended for research, demonstration, and educational purposes

*Not Medical Advice*: Should not replace clinical judgment or professional medical advice

*Not for Type 2 Diabetes*: This calculator is not intended for patients with Type 2 Diabetes

*Individual Results Vary*: Actual patient outcomes may differ significantly from modeled predictions

*Consult Healthcare Provider*: Always discuss treatment options with a qualified healthcare professional

## 🛠️ **Technical Details**

### **Technologies Used**

1. HTML5: Structure and content
   
2. CSS3: Styling with gradients and responsive grid layout

3. JavaScript: Calculation logic and interactivity

4. Chart.js: Interactive chart visualization library (CDN)

5. Browser Compatibility: Chrome 90+, Firefox 88+, Safari 14+, Edge 90+

## **Model Information**

The prediction model uses:

1. Base weight loss rates from clinical trial data by dose

2. Adjustment factors for age, sex, BMI, and diabetes status

3. Logistic time curve to model realistic weight loss progression

4. IQR bands derived from SURMOUNT-1 trial categorical data


