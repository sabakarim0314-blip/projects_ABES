
| 8 | Average fee by department | `groupby().mean()` |
| 9 | Volume by date and department | `groupby`, `crosstab` |
| 10 | New vs follow-up waiting time | `groupby().agg()` |
| 11 | Median, quartiles, std deviation | NumPy: `median`, `percentile`, `std` |
| 12 | Long waits using IQR | Q1 - 1.5×IQR, Q3 + 1.5×IQR |
| 13 | Waiting-time categories | `pd.cut()` |
| 14 | Estimated fees (attended only) | `sum()` |
| 15 | Five recommendations | Based on results |

## 📊 Key Findings

- **Total appointments:** 3,000 (after removing 12 duplicates)
- **Attendance:** 71.77% attended, 19.50% no-show, 8.73% cancelled
- **SMS reminders:** no-show rate is **12.95% with SMS** vs **29.54% without SMS**
- **Highest no-show:** Dermatology (24.60%), followed by Orthopedics (24.18%)
- **Longest average wait:** General Medicine (45.66 min)
- **New vs follow-up:** 41.31 min vs 32.47 min
- **Waiting time stats:** median 35 min, Q1 26, Q3 44, std dev 17.30
- **Unusually long waits (IQR):** 24 appointments above 71 min
- **Estimated fees (attended):** Rs. 10,30,400

## 💡 Operational Recommendations

1. Send SMS reminders for all appointments to reduce no-shows.
2. Give extra attention to Dermatology and Orthopedics with reminder calls and a waiting list to refill empty slots.
3. Reduce waiting time in General Medicine with an extra doctor or triage desk at peak hours.
4. Add online pre-registration to reduce the longer wait of new patients.
5. Move staff towards the busiest department and weekday, and review IQR-outlier waits weekly.

## ⚠️ Limitations

- Data is synthetic, so results demonstrate the method rather than a real hospital.
- Operational data only; no clinical or medical # 🏥 Hospital Appointment Operations Analysis

**Project 9 | Industry: Healthcare Operations | Course Project: Python for Data Analysis (NumPy & Pandas)**

> **Student Name:** _Your Name_  
> **Roll No / Enrollment No:** _Your ID_  
> **Course:** _Course Name_  
> **Submitted To:** _Instructor Name_

---

## 📌 Project Overview

Hospitals lose time and money when patients miss appointments or wait too long. This project analyzes
hospital appointment records to understand **attendance, waiting times and department workload**, and to
find **operational bottlenecks**.

> ⚠️ This is an **operational** dataset, not a clinical one. No medical conclusions are made.

## 🎯 Objectives

- Clean the appointment data (missing waiting times, duplicate IDs)
- Measure attendance and no-show rates
- Find which departments have the longest waits and most no-shows
- Check whether SMS reminders reduce no-shows
- Detect unusually long waiting times using the IQR method
- Estimate consultation fee income
- Suggest practical operational improvements

## 🛠️ Technologies Used

| Tool | Purpose |
|------|---------|
| Python 3.9+ | Programming language |
| Pandas | Data loading, cleaning, grouping, crosstab, binning |
| NumPy | Median, quartiles, standard deviation, IQR |

## 📁 Repository Structure

```
hospital_appointment_analysis/
├── data/
│   └── 09_hospital_appointments.csv        # Dataset (3,012 records)
├── docs/
│   └── SRS_Hospital_Appointment_Analysis.docx
├── outputs/                                # All generated results
│   ├── analysis_report.txt
│   ├── department_summary.csv
│   ├── attendance_status_summary.csv
│   ├── sms_reminder_vs_attendance.csv
│   ├── volume_by_date_department.csv
│   ├── waiting_time_statistics.csv
│   ├── waiting_time_outliers.csv
│   ├── waiting_time_bands.csv
│   ├── waiting_bands_by_department.csv
│   ├── waiting_time_by_appointment_type.csv
│   ├── estimated_fee_summary.csv
│   ├── duplicate_records.csv
│   └── cleaned_appointments.csv
├── generate_dataset.py                     # Creates the dataset
├── main.py                                 # Complete analysis (Tasks 1-15)
├── create_srs.py                           # Builds the SRS document
├── requirements.txt
└── README.md
```

## 🗂️ Dataset Description

| Column | Description |
|--------|-------------|
| Appointment_ID | Appointment number |
| Patient_ID | Anonymous patient code |
| Appointment_Date | Date of appointment |
| Department | Hospital department (8 departments) |
| Doctor_ID | Anonymous doctor code |
| Appointment_Type | New / Follow-up |
| SMS_Reminder | Yes / No |
| Attendance_Status | Attended / No-Show / Cancelled |
| Waiting_Time_Min | Waiting time in minutes |
| Consultation_Fee | Consultation fee (Rs.) |

The dataset is synthetic and created with `generate_dataset.py` (fixed random seed, so results are repeatable).

## ▶️ How to Run

```bash
# 1. Clone the repository
git clone <your-repository-link>
cd hospital_appointment_analysis

# 2. Install libraries
pip install numpy pandas

# 3. (Optional) regenerate the dataset
python generate_dataset.py

# 4. Run the analysis - results are saved in the outputs/ folder
python main.py
```

## ✅ Tasks Completed

| # | Task | Method |
|---|------|--------|
| 1 | Load and inspect records | `read_csv`, `head`, `info`, `describe` |
| 2 | Handle missing waiting times | `isnull`, median fill by department |
| 3 | Check duplicate Appointment_ID | `duplicated`, `drop_duplicates` |
| 4 | Total appointments and attendance % | `value_counts(normalize=True)` |
| 5 | Average waiting time by department | `groupby().mean()` |
| 6 | Highest no-show departments | `groupby().agg()` |
| 7 | SMS Yes vs No no-show rate | `crosstab()` |conclusions.

## 📄 Deliverables

- SRS document: `docs/SRS_Hospital_Appointment_Analysis.docx`
- Source code: `main.py`, `generate_dataset.py`
- GitHub repository link: _add your link here
