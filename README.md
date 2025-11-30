# 🏥 Hospital ER Analytics — Power BI Dashboard

A comprehensive **Emergency Room (ER) Analytics Dashboard** built using **Power BI**, focusing on patient flow, wait time efficiency, admission patterns, satisfaction insights, and referral behavior.  
This project was developed as part of my internship, where I handled the dashboard **end-to-end** — data cleaning, modeling, DAX measures, visual design, and documentation.

---

## 📸 Dashboard Preview (Screenshots)

### **1. Monthly View**
![Monthly View](./screenshots/01_monthly_view.png)

### **2. Consolidated Overview**
![Consolidated View](./screenshots/02_consolidated_view.png)

### **3. Patient Details & Demographics**
![Patient Details](./screenshots/03_patient_details.png)

### **4. Key Takeaways Summary**
![Key Takeaways](./screenshots/04_key_takeaways.png)

---

## 📄 Full Dashboard (PDF)
View or download the complete 4-page dashboard:

👉 **[dashboard.pdf](./dashboard.pdf)**

---

## 📁 PBIX File (Interactive Dashboard)
The PBIX file **cannot be previewed on GitHub**.

To explore the live interactive dashboard, download the PBIX:

👉 **[dashboard.pbix](./dashboard.pbix)**  
(Open it in **Power BI Desktop**)

If GitHub download fails, use this Google Drive backup (optional):

🔗 *Add Drive link here if you choose to upload*

---

## 🧼 Data Cleaning & Transformation  
Detailed cleaning steps used in Power Query:

👉 **[Cleaning Steps](./docs/cleaning_steps.md)**

Includes:
- Handling missing values  
- Standardizing Gender, Race, Referral fields  
- Extracting Date/Time features  
- Removing duplicates  
- Creating age groups  
- Outlier treatment  
- Building dimension tables  

---

## 🔢 DAX Measures Documentation  
All DAX calculations used in KPIs and visuals:

👉 **[DAX Measures](./docs/dax_measures.md)**

Covers:
- Total Patients  
- Avg Wait Time  
- % Seen within 30 minutes  
- Admission Rate  
- Referral Counts  
- Gender/Race distribution  
- Hourly/Day heatmap measures  

---

## 🧩 Data Model  
Below is the relational data model used inside Power BI:

![Data Model](./docs/model_schema.png)

---

## 🛠️ Tools & Technologies

| Tool | Usage |
|------|-------|
| **Power BI Desktop** | Dashboard building, visuals, data modeling |
| **Power Query** | Data cleaning & preprocessing |
| **DAX** | Calculated measures & KPIs |
| **GitHub** | Project documentation & hosting |
| **Google Drive (optional)** | PBIX hosting if needed |

---

## 📊 Key Insights From Dashboard
- Patient wait times show peak congestion during specific hours.  
- Referral patterns reveal departments with highest follow-ups.  
- Admission rates correlate with severity and patient demographics.  
- A clear performance metric shows % served within 30 minutes.  
- Satisfaction scores help evaluate overall ER experience.

---

## 📂 Project Structure

```
hospital-er-analytics/
├─ README.md
├─ dashboard.pdf
├─ dashboard.pbix        
├─ screenshots/
│   ├─ 01_monthly_view.png
│   ├─ 02_consolidated_view.png
│   ├─ 03_patient_details.png
│   ├─ 04_key_takeaways.png
├─ docs/
│   ├─ dax_measures.md
│   ├─ model_schema.png
│   ├─ cleaning_steps.md
