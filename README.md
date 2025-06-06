# Government-Health-Facility-Ranking
## Using Microsoft Excel

### Overview
An Excel-based Health Facility Performance Monitoring Tool with Automated Scoring, Ranking, and Reporting Capabilities.

------
### Problem Statement:
There was no standardized method to evaluate and compare the performance of government health facilities across Bihar.
Manual reviews led to inconsistencies, delays, and difficulty in identifying low-performing districts.
Key health indicators lacked a unified scoring system for accurate benchmarking.
A transparent, automated ranking mechanism was needed to support data-driven decision-making.

---------

### Data Source:
https://dashboard-1.bhavyabiharhealth.in/bhavya_app_dashboard.php
An internal dashboard for BHAVYA project

------------

### Methodology:

**1.	Indicator Selection:**
   
1.1.	Registration Allocation

1.2.	Journey Time

1.3.	Online Consultations

1.4.	Vitals Taken

1.5.	Provisional Diagnosis

1.6.	Specifically for District Hospitals

1.6.1.	No. of Admissions	

1.6.2.	No. of Referrals	

1.6.3.	No. of Deaths

**2.	Data Collection:**
Data for each indicator was collected weekly/monthly from district and facility-level health records across Bihar.

 **3.	Normalization:**
All indicator values were normalized to percentages based on max achievable or target values:
Normalized Score = (Actual Value / Maximum or Target Value) × 100

**4.	Weight Assignment:**
Each indicator was assigned a pre-defined weight based on its importance (e.g., 0.125, 0.2).
These weights were agreed upon by the health department or project stakeholders.

**5.	Weighted Scoring:**
Final performance score for each facility/district was computed using: 
Final Score = Σ (Normalized Indicator × Weight)

**6.	Ranking Calculation:**
Using Excel formulas (RANK.EQ() or manual sorting), facilities were ranked within their category (DH, SDH/RH, CHC/PHC) based on total scores.

---------------

### Conclusion:
The Ranking tool project applies a weighted multi-indicator scoring model to evaluate health facility performance across Bihar. Key metrics like registration allocation, journey time, and online consultations are normalized, weighted, and aggregated to compute district-wise scores. Excel formulas such as % calculations, weighted scores, RANK.EQ(), and IFS logic are used for dynamic ranking. This analysis helps the Health Department identify strengths, gaps, and areas needing focused intervention.

--------------

### Snapshots:

1.	 ![image](https://github.com/user-attachments/assets/5d2ca549-f18e-4806-bf9d-a2141f075ac1)


2.	 ![image](https://github.com/user-attachments/assets/13a2939d-3a1d-411d-80b8-0e1d5eaff9da)


3.	 ![image](https://github.com/user-attachments/assets/d5ba7b62-b1d7-4f28-b207-677e204c40fd)


------------

### Formula Used:

1.	***((#REF!)/MAX($C$13:$C$48))*100*** - Calculates percentage score by comparing a value to the maximum in a column.
2.	***IFERROR((#REF!/$B$10)*100,0)*** - Converts a value to percentage of a benchmark (with error handling).
3.	***IFERROR((#REF!/#REF!)*100,0)*** - Calculates ratio-based percentage while avoiding errors (division).
4.	***IFERROR((#REF!/#REF!)*100,0)*** - Similar to above; used for indicator normalization with error fallback.
5.	***IFERROR((#REF!/#REF!)*100,0)*** - Another indicator-wise percentage calculation with fallback.
6.	***((#REF!)/MAX($H$13:$H$48))*100*** - Normalizes a value relative to the highest value in another column.
7.	***IFERROR((#REF!/#REF!)*100,0)*** - Converts data into percentage format while handling possible errors.
8.	***IFERROR((#REF!/#REF!)*100,0)*** - Calculates another performance indicator in % safely.
9.	***SUMPRODUCT(A1,$C$2)*** - Multiplies A1 by a weight/value in C2 for weighted scoring.
10.	***SUMPRODUCT(B1,$C$3)*** - Weighted score from B1 using C3 as weight.
11.	***SUMPRODUCT(C1,$C$4)*** - Weighted score from C1 using C4 as weight.
12.	***SUMPRODUCT(D1,$C$5)*** - Weighted score from D1 using C5 as weight.
13.	***SUMPRODUCT(E1,$C$6)*** - Weighted score from E1 using C6 as weight.
14.	***SUMPRODUCT(F1,$C$7)*** - Weighted score from F1 using C7 as weight.
15.	***SUMPRODUCT(G1,$C$8)*** - Weighted score from G1 using C8 as weight.
16.	***SUMPRODUCT(H1,$C$9)*** - Weighted score from H1 using C9 as weight.
17.	***SUM(I1,K1,L1,M1,N1)-SUM(J1,O1,P1)*** - Final score calculation by adding positive indicators and subtracting penalties.
18.	***RANK.EQ(Q1,$AA$13:$AA$48)*** - Assigns rank to a facility based on final score among all facilities.



