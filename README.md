# 🏥 Healthcare Waitlist Dashboard | Power BI

This repository contains a **Power BI dashboard** designed to visualize and analyze **healthcare waitlist data**. The dashboard provides **actionable insights** into patient wait times, case types, specialties, and trends over time, helping healthcare professionals improve service efficiency.

## 📊 **See the Full Dashboard Here**  
[🔗 Power BI Healthcare Waitlist Dashboard](https://app.powerbi.com/view?r=eyJrIjoiMGEzZTA1YTktZjJiOC00Y2UyLWE2OTYtOWNkZDYwNjgyYTliIiwidCI6IjE3ZjFhODdlLTJhMjUtNGVhYS1iOWRmLTlkNDM5MDM0YjA4MCIsImMiOjF9)  

---

## 📌 **Key Features**
- **Total Waitlist Overview**: Provides a summary of the total number of patients waiting for treatment.
- **Case Type Breakdown**: Analysis of **Outpatient, Day Case, and Inpatient** waitlists.
- **Specialty-wise Analysis**: Insights into the **top 5 specialties** with the highest wait times.
- **Waitlist Trends**: Monthly trend analysis for **Day Cases & Inpatients**.
- **Time Band vs. Age Profile**: Helps identify how long different age groups wait for treatment.
- **Detailed Case Type Analysis**: Drill-down capabilities for analyzing waitlist data based on different medical specialties.
- **Interactive Filters**: Users can filter by **case type, specialty, age profile, and time band** for dynamic analysis.

---

## 🏥 **Healthcare Dashboard Sections & Image References**

### **1️⃣ Home Page - Main Dashboard**
![🏠 Home Page](/home.png)  
The **home page** provides a high-level overview of total waitlist numbers, case type splits, and key indicators. It includes:
- **Total Waitlist Comparison (YoY)**
- **Case Type Split (Outpatient, Day Case, Inpatient)**
- **Key Indicators: Waitlist by Age Profile**
- **Monthly Trend Analysis**  

### **2️⃣ Tooltip - Detailed Insights**
![ℹ️ Tooltip](/tooltip.png)  
The **tooltip** provides additional insights when hovering over visual elements, revealing more details about wait times, trends, and data splits.

### **3️⃣ Case Type Breakdown**
![📂 Case Type Breakdown](/casetype.png)  
This section allows users to filter data based on case types, such as **Outpatient, Day Case, and Inpatient**. The data dynamically updates to reflect selections.

### **4️⃣ Specialty Name Analysis**
![🩺 Specialties](/specialityname.png)  
A **deep dive into specialties**, showing average and median wait times for each medical specialty. Helps identify which specializations have the longest waiting lists.

### **5️⃣ Detailed View of Patient Cases**
![📊 Detail View](/detailview.png)  
A **table-based detailed view** that provides patient waitlist numbers broken down by:
- **Age Groups**
- **Specialty**
- **Case Type**
- **Time Bands**  

---

## 📂 **Files Included**
- **Healthcare_Waitlist_Dashboard.pbix** – The Power BI dashboard file.
- **Data Sources** – The datasets used for the analysis.
- **README.md** – This documentation file.

---

## ⚡ **🛠 Technologies Used**
	•	Power BI – Data visualization and dashboard creation
	•	DAX (Data Analysis Expressions) – Calculated measures and aggregations
	•	SQL & Data Transformation – Data cleaning and pre-processing
## **Key DAX Functions**

// Total Waitlist
TotalWaitlist = SUM(WaitlistData[Total Patients])

// Year-over-Year Comparison
YoY_Waitlist_Change = 
    VAR CurrentYear = CALCULATE([TotalWaitlist], SAMEPERIODLASTYEAR(DateTable[Date]))
    RETURN DIVIDE([TotalWaitlist] - CurrentYear, CurrentYear, 0)

// Waitlist by Case Type
Waitlist_By_CaseType = CALCULATE([TotalWaitlist], FILTER(WaitlistData, WaitlistData[Case Type] = "Inpatient"))

// Average Wait Time
Avg_Wait_Time = AVERAGE(WaitlistData[Wait Time in Days])


   
