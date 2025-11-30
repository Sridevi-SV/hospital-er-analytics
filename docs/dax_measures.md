# DAX Measures — Hospital ER Analytics

This document lists all DAX measures used in the Hospital ER Dashboard.  
These measures support key KPIs such as total patients, average wait time, admission rates, referral patterns, and patient satisfaction.

---

## 1. Total Patients
```DAX
Total Patients = DISTINCTCOUNT(Patient[Patient Id])
```
Counts unique patients in the dataset.

---

## 2. Average Wait Time (Minutes)
```DAX
Avg Wait Time = AVERAGE(Patient[Waittime])
```
Calculates the mean wait time experienced by patients.

---

## 3. Patient Satisfaction Score (Average)
```DAX
Avg Satisfaction Score = AVERAGE(Patient[Satisfaction Score])
```
Measures the overall patient satisfaction level.

---

## 4. Patients Seen Within 30 Minutes
```DAX
Patients Within 30 = 
CALCULATE(
    COUNTROWS(Patient),
    FILTER(Patient, Patient[Waittime] <= 30)
)
```
Counts patients who were served within the target of 30 minutes.

---

## 5. Percentage Seen Within 30 Minutes
```DAX
Pct Within 30 = 
DIVIDE([Patients Within 30], [Total Patients], 0)
```
Shows performance against the 30-minute wait target.

---

## 6. Total Patients Referred
```DAX
Total Referred = 
CALCULATE(
    COUNTROWS(Patient),
    Patient[Department Referral] <> "None"
)
```
Counts patients who required referrals.

---

## 7. Admission Count
```DAX
Total Admitted = 
CALCULATE(
    COUNTROWS(Patient),
    Patient[Admission status] = "Admitted"
)
```
Number of patients who were admitted.

---

## 8. Admission Percentage
```DAX
Admission Pct = 
DIVIDE([Total Admitted], [Total Patients], 0)
```
Percentage of admitted patients.

---

## 9. Patients by Gender (Used in Donut Visual)
```DAX
Male Count = CALCULATE([Total Patients], Patient[Gender] = "Male")

Female Count = CALCULATE([Total Patients], Patient[Gender] = "Female")
```

---

## 10. Patients by Race
```DAX
Patients by Race = COUNTROWS(Patient)
```
(Used with Race column as axis)

---

## 11. Patients by Age Group
```DAX
Patients by Age Group = COUNTROWS(Patient)
```
(Used with Age Group dimension table or grouped column)

---

## 12. Hourly Heatmap Measure
```DAX
Visits Count = COUNTROWS(Patient)
```
Used in the matrix visual grouped by day and hour.

---

## 13. Date Range Slicer Support (Optional)
```DAX
Min Date = MIN(Patient[Patient Admin Date])
Max Date = MAX(Patient
