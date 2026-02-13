# **Weight Loss Prediction Calculator with Tirzepatide**

A web-based calculator that predicts personalized weight loss trajectories over 72 weeks for patients using Tirzepatide, with interactive visualizations and IQR confidence bands.

## 🎯 **Features**

1. Personalized Predictions: Calculates weight loss based on individual patient characteristics
   
2. Interactive Chart: Dual-axis visualization showing both weight (kg) and weight loss percentage

3. IQR Confidence Bands: Displays typical variation ranges based on clinical trial data

4. Responsive Design: Works seamlessly on desktop and mobile devices

5. Real-time Updates: Instant calculations and graph generation

6. Detailed Timeline: Week-by-week predictions at key timepoints (0, 4, 8, 12, 24, 36, 52, 72 weeks)
   
## 📊 **What It Does**

This calculator estimates weight loss trajectories for patients prescribed Tirzepatide by considering:

1. Current weight and height (BMI calculation)
   
2. Age and biological sex
   
3. Tirzepatide dosage (5mg, 10mg, or 15mg)
   
4. Diabetes status (No Diabetes or Prediabetes)
   
The tool uses a logistic growth model calibrated with clinical trial data to project:

1. Expected weight at each timepoint
   
2. Body Mass Index (BMI) changes
   
3. Percentage of total weight loss
   
4. Interquartile range (IQR) bands showing typical variation
   
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

(iv) Sex (Male/Female)

(v) Select Tirzepatide dose (5mg, 10mg, or 15mg)

(vi) Diabetes status

Click **"Calculate Weight Loss Trajectory"**

### **View results:**

Interactive graph and detailed table with predictions

### 📈 **Interpretation**

#### **Graph Elements**

1. Blue Line: Predicted weight (kg) over time
   
2. Pink Line: Predicted weight loss percentage

3. Shaded Bands: Interquartile ranges (IQR) showing where 50% of similar patients typically fall

4. Data Points: Weekly predictions at clinical trial timepoints

5. Table Data: Each row shows

(i) Timepoint: Baseline or week number

(ii) Weight (kg): Predicted body weight

(iii) BMI (kg/m²): Body Mass Index

(iv) Weight Loss (%): Cumulative percentage weight loss from baseline

## ⚠️ **Important Disclaimers**

*Educational Purpose Only*: This tool is for research and educational purposes

*Not Medical Advice*: Should not replace clinical judgment or professional medical advice

*Not for Type 2 Diabetes*: This calculator is not intended for patients with Type 2 Diabetes

*Individual Results Vary*: Actual outcomes may differ significantly from predictions

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


