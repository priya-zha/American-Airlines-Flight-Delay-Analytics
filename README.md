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

## 📁 Project Structure

```
├── American_Airlines_Flight_Analytics.pbix   # Power BI dashboard file
├── screenshots/                              # Dashboard screenshots
│   ├── delay_causes_by_destination.png
│   ├── scheduled_vs_actual_times.png
│   ├── taxi_out_distribution.png
│   └── departure_delays_by_tail_number.png
├── data/                                     # Raw / processed data (if applicable)
├── analysis.py                               # Python data cleaning & analysis scripts
└── README.md                                 # Project documentation
```

> 📂 **To view the dashboard:** Download `American_Airlines_Flight_Analytics.pbix` and open it in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free).

---

## 📊 Dashboard Highlights

### 1. 🔴 Delay Causes by Destination Airport
Bar charts breaking down delay causes (weather, carrier, late aircraft, NAS, security) per destination airport — revealing which routes are most delay-prone and why.

### 2. 📈 Scheduled vs Actual Flight Times
Line charts comparing scheduled departure/arrival times against actual times across all routes — exposing systemic scheduling inefficiencies.

### 3. 🛬 Taxi-Out Time Distribution by Flight Number
Visualized taxi-out time distribution per flight number to assess ground delay patterns and identify high-congestion aircraft.

### 4. 🛩️ Departure Delays by Tail Number
Correlation analysis of departure delays by individual tail numbers — identifying specific aircraft with persistent delay patterns, enabling targeted maintenance planning.

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

- **Weather and late aircraft** are the top two causes of delays at DFW across most destination airports
- Certain **tail numbers** consistently show higher departure delay rates, suggesting maintenance or scheduling issues
- **Taxi-out times** vary significantly by flight number, pointing to gate assignment and ground crew inefficiencies
- **Scheduled vs actual time gaps** are widest on long-haul routes, indicating buffer time miscalculations

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
3. Explore the interactive dashboard

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
