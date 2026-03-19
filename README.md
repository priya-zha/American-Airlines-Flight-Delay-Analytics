
# ✈️ Flight Delay & Performance Analytics — American Airlines

> **Operational insights from 700,000+ flight records at DFW Airport using Power BI & Python**

---

## 📌 Description

This project analyzes over **700,000 flight records** from **Dallas/Fort Worth (DFW) Airport** to uncover patterns in flight delays, identify root causes, and deliver actionable operational insights for American Airlines. The analysis spans delay causes, departure performance, taxi-out times, and tail number-level correlations — all visualized through an interactive **Power BI dashboard**.

A **dimensional model (star schema)** was designed to structure raw data into fact and dimension tables for efficient querying and reporting in Power BI.

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| Python | Data cleaning, preprocessing & analysis |
| Pandas | Data manipulation and transformation |
| Power BI | Interactive dashboard and visual reporting |
| Star Schema (Dimensional Modeling) | Data warehouse structure for efficient querying |
| Correlation Analysis | Statistical analysis of delay factors |

---

## 📊 Dashboard Screenshots

### Page 1 — Flight Delay Analysis by Time, Destination & Delay Type

![Flight Delay Analysis](screenshots/dashboard_delay_analysis.png)

> Departure delay trends over time, average flights per day vs average delays by destination airport, weather delay patterns, and delay breakdown by type (carrier, weather, late aircraft).

---

### Page 2 — Flight Performance Analysis by Airport, Aircraft & Schedule

![Flight Performance Analysis](screenshots/dashboard_performance_analysis.png)

> Flight delay breakdown by cause and destination airport, taxi-out time distribution by flight number, scheduled vs actual elapsed time comparison, and average departure delay by tail number.

---

## 📁 Project Structure

```
├── American_Airlines_Flight_Analytics.pbix   # Power BI dashboard file
├── screenshots/                              # Dashboard screenshots
│   ├── dashboard_delay_analysis.png
│   └── dashboard_performance_analysis.png
├── data/                                     # Raw / processed data (if applicable)
├── analysis.py                               # Python data cleaning & analysis scripts
└── README.md                                 # Project documentation
```

> 📂 **To view the dashboard:** Download `American_Airlines_Flight_Analytics.pbix` and open it in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free).

---

## 📊 Dashboard Highlights

### 1. 🔴 Delay Analysis by Time & Destination
Average departure delays over the full year with spikes highlighted — weather and late aircraft dominate. Average flights per day vs average flight delays broken down by destination airport (LAX, PHX, MIA, SAT, LAS, etc.).

### 2. ⏱️ Delay Type Breakdown
Multi-series time chart comparing weather delays, carrier delays, and late aircraft delays — revealing that **late aircraft arrival** is the primary compounding delay factor.

### 3. ✈️ Flight Performance by Airport & Aircraft
Stacked bar charts breaking down total delay minutes by cause (carrier, late aircraft, NAS, security, weather) per destination airport — SAT and LAX show the highest total delays.

### 4. 🛬 Taxi-Out Time Distribution by Flight Number
Bar chart showing average taxi-out time across 3,500+ flight numbers — identifying congestion patterns and high-delay flight numbers.

### 5. 🛩️ Departure Delays by Tail Number
Scatter plot correlating tail numbers with average departure delay, colored by flight number — pinpointing specific aircraft with consistently poor on-time performance.

### 6. 📅 Scheduled vs Actual Elapsed Time
Line chart comparing scheduled vs actual elapsed flight times — revealing periods where actual flight times significantly diverge from schedule.

---

## 🏗️ Data Model — Star Schema

```
                    ┌─────────────────┐
                    │   FACT_FLIGHTS  │
                    │─────────────────│
                    │ flight_id (PK)  │
                    │ date_key (FK)   │
                    │ aircraft_key(FK)│
                    │ route_key (FK)  │
                    │ delay_minutes   │
                    │ delay_cause     │
                    │ taxi_out_time   │
                    │ scheduled_dep   │
                    │ actual_dep      │
                    └────────┬────────┘
           ┌─────────────────┼──────────────────┐
           ▼                 ▼                  ▼
  ┌─────────────┐   ┌─────────────────┐  ┌───────────────┐
  │  DIM_DATE   │   │  DIM_AIRCRAFT   │  │   DIM_ROUTE   │
  │─────────────│   │─────────────────│  │───────────────│
  │ date_key    │   │ aircraft_key    │  │ route_key     │
  │ year        │   │ tail_number     │  │ origin        │
  │ month       │   │ aircraft_type   │  │ destination   │
  │ day         │   │ airline         │  │ distance      │
  └─────────────┘   └─────────────────┘  └───────────────┘
```

---

## 🔍 Key Insights

- **Late aircraft arrival** is the single largest driver of cascading delays across DFW routes
- **SAT, LAX, and AUS** show the highest total delay volumes by destination
- Certain **tail numbers** consistently show higher departure delay rates, suggesting maintenance or scheduling issues
- **Taxi-out times** vary significantly by flight number, pointing to gate assignment and ground crew inefficiencies
- A notable **spike in departure delays** occurs in late November/December 2024 — likely weather-driven
- **Scheduled vs actual time gaps** widen on specific routes and tail numbers, enabling targeted scheduling fixes

---

## ⚙️ How to Run

### Python Analysis
```bash
git clone https://github.com/priya-zha/American-Airlines-Flight-Delay-Analytics.git
cd American-Airlines-Flight-Delay-Analytics
pip install pandas matplotlib seaborn
python analysis.py
```

### Power BI Dashboard
1. Download `American_Airlines_Flight_Analytics.pbix` from this repo
2. Open with [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free download)
3. Explore the interactive dashboard with Year, Destination Airport, and Flight Number filters

---

## 📋 Requirements

- Python 3.6+
- Pandas, Matplotlib, Seaborn
- Power BI Desktop (free) for `.pbix` file

---

## 👩‍💻 Author

**Priya Jha** — AI/ML Engineer | Data Analytics  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/priya-jha-105866167/)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=flat&logo=github&logoColor=white)](https://github.com/priya-zha)
[![Email](https://img.shields.io/badge/Email-D14836?style=flat&logo=gmail&logoColor=white)](mailto:pj35134@gmail.com)
