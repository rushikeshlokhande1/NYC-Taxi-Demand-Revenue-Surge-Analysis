# 🚕 NYC Taxi Demand, Revenue & Surge Analysis (2026)

## 📌 Project Overview

This project analyzes **NYC Yellow Taxi trip data** to understand taxi demand, revenue patterns, location-based performance, and the potential impact of demand-based surge pricing.

The analysis covers approximately **232K taxi trips** and combines **Python, SQL, Power BI, and Machine Learning** to perform data cleaning, feature engineering, exploratory analysis, business intelligence, surge-pricing simulation, and revenue prediction.

---

## 🎯 Business Objectives

The project focuses on answering key business questions:

* When is taxi demand highest and lowest?
* Which hours generate the most revenue?
* Which NYC boroughs contribute the most trips and revenue?
* Which pickup zones generate the highest revenue?
* How could demand-based surge pricing affect revenue?
* Can taxi fare/revenue be predicted using trip characteristics?

---

## 🛠️ Technologies Used

* **Python**

  * Pandas
  * NumPy
  * Matplotlib
  * Seaborn
  * Scikit-learn
* **SQL**
* **Power BI**
* **Jupyter Notebook / Google Colab**
* **Machine Learning**

---

# 🔹 1. Data Cleaning & Preprocessing

The raw NYC Yellow Taxi dataset was cleaned and prepared for analysis.

The dataset contains approximately:

**231,954 taxi trips and 25 analytical columns**

The data includes:

* Pickup and drop-off timestamps
* Trip distance
* Passenger count
* Pickup and drop-off locations
* Fare amount
* Tip amount
* Tolls
* Taxes
* Total revenue
* Payment type

---

# 🔹 2. Feature Engineering

Several analytical features were created to better understand taxi demand and revenue.

### Trip-level features

* `trip duration min`
* `pickup hour`
* `pickup day`
* `pickup weekday`

### Revenue features

* `revenue_per_mile`
* `revenue_per_minute`
* `tip_percentage`

### Surge-pricing features

* `demand_percentile`
* `surge_multiplier`
* `simulated_total_amount`

These features were used for demand analysis, revenue analysis, and surge-pricing simulation.

---

# 🔹 3. Demand & Revenue Analysis

Using Python and Power BI, I analyzed taxi activity across different hours of the day.

### Key observations

* Taxi demand is relatively low during the early-morning hours.
* Demand increases significantly from the morning onward.
* The highest trip volume occurs around **15:00**, with approximately **16.4K trips**.
* Revenue follows a similar pattern to trip demand.
* Hour **15** generates approximately **$1.36M** in original revenue.

This helped identify the relationship between **trip volume and revenue generation throughout the day**.

---

# 🔹 4. Location-Based Revenue Intelligence

The Power BI dashboard analyzes revenue and trip volume across NYC boroughs and pickup zones.

### Borough-level analysis

**Manhattan** contributes the largest share of the analyzed revenue and trip volume:

* Revenue: approximately **$10.5M**
* Trips: approximately **132K**

Other major contributors include:

* Queens
* Brooklyn
* Bronx

### Top Revenue-Generating Zones

The analysis identified high-revenue zones including:

* LaGuardia Airport — approximately **$1.23M**
* JFK Airport — approximately **$1.18M**
* Times Sq/Theatre District — approximately **$0.89M**
* Newark Airport — approximately **$0.69M**
* Midtown South
* Midtown Center
* Murray Hill
* Clinton East
* East Chelsea

This provides a location-level view of where taxi revenue is concentrated.

---

# 🔹 5. Surge Pricing Simulation

A demand-based surge-pricing simulation was created to estimate the potential revenue impact of applying dynamic pricing.

A **demand percentile** was calculated and mapped to a corresponding surge multiplier.

The simulated revenue was then calculated using the surge multiplier.

### Revenue Uplift Formula

```text
Revenue Uplift %
=
((Surge Revenue - Original Revenue) / Original Revenue) × 100
```

### Simulation Results

| Metric                  |   Value |
| ----------------------- | ------: |
| Original Revenue        | $18.10M |
| Simulated Surge Revenue | $22.62M |
| Revenue Uplift          |  24.97% |

Under the simulation assumptions, applying the modeled surge multipliers increases the calculated revenue from **$18.10M to $22.62M**, representing a **24.97% simulated revenue uplift**.

> **Note:** This is a simulation based on the project's assumed surge-pricing rules. It does not represent actual NYC taxi pricing or observed real-world revenue uplift.

---

# 🔹 6. Power BI Dashboard

The project includes multiple Power BI dashboard pages.

### Dashboard 1 — NYC Taxi Demand & Revenue Analytics

Key KPIs:

* **232K** total trips
* **$18.10M** total revenue
* **$78.02** average fare
* **24.97%** simulated revenue uplift

Visualizations include:

* Trips by hour
* Revenue by pickup hour
* Demand patterns throughout the day

### Dashboard 2 — Location-Based Revenue Intelligence

Visualizations include:

* Revenue by borough
* Trips by borough
* Top 10 revenue-generating zones

### Dashboard 3 — Surge Pricing Impact

Visualizations include:

* Original revenue vs. simulated surge revenue
* Revenue by hour
* Total original revenue
* Simulated surge revenue
* Revenue uplift percentage

---

# 🔹 7. SQL Analysis

SQL was used to perform business-oriented analysis on the taxi dataset.

Examples include:

* Trips by pickup hour
* Revenue by hour
* Average fare
* Average tip
* Average trip duration
* Revenue comparisons
* Window functions such as `LAG()` and `LEAD()`
* Grouping and aggregation
* CTE-based analysis
---

# 🔹 8. Machine Learning — Fare Prediction

A **Linear Regression** model was developed to predict taxi `total_amount` using trip characteristics.

Initial features included:

* `trip_distance`
* `trip duration min`
* `passenger_count`
* `pickup hour`
* `pickup_weekday`
* `PULocationID`
* `DOLocationID`
* `payment_type`
* `surge_multiplier`
Additional experiments explored other relevant features such as:

* Passenger count
* Pickup hour
* Pickup weekday
* Surge multiplier

### Model Evaluation

The regression model was evaluated using:

* **MAE — Mean Absolute Error**
* **RMSE — Root Mean Squared Error**
* **R² Score**

The purpose of the ML component was to explore whether trip characteristics could explain and predict taxi revenue.

---

# 📊 Key Project Insights

### Demand

Taxi demand varies significantly throughout the day, with the highest observed trip volume occurring around the afternoon period.

### Revenue

Revenue generally follows the overall demand pattern, with higher trip volumes contributing to higher hourly revenue.

### Location

Manhattan represents the largest revenue and trip-volume contributor in the analyzed dataset.

### Airports

Airport-related zones such as **LaGuardia Airport and JFK Airport** appear among the highest revenue-generating zones.

### Surge Pricing

The modeled surge-pricing scenario produces a **24.97% simulated revenue uplift**, increasing calculated revenue from **$18.10M to $22.62M** under the project's assumptions.

---

# 🔄 Project Workflow

```text
NYC Taxi Dataset
       ↓
Data Cleaning
       ↓
Feature Engineering
       ↓
Exploratory Data Analysis
       ↓
SQL Business Analysis
       ↓
Power BI Dashboard
       ↓
Demand Analysis
       ↓
Surge Pricing Simulation
       ↓
Machine Learning
       ↓
Model Evaluation
       ↓
Business Insights
```

---

# 📁 Project Structure

```text
NYC-Taxi-Demand-Revenue-Analysis/
│
├── data/
│   └── taxi_dataset.csv
│
├── notebooks/
│   ├── data_cleaning.ipynb
│   ├── exploratory_analysis.ipynb
│   └── machine_learning.ipynb
│
├── sql/
│   └── taxi_analysis.sql
│
├── powerbi/
│   └── NYC_Taxi_Analysis.pbix
│
├── images/
│   ├── demand_revenue_dashboard.png
│   ├── location_revenue_dashboard.png
│   └── surge_pricing_dashboard.png
│
└── README.md
```

---

# 🚀 Skills Demonstrated

**Python | Pandas | NumPy | SQL | Power BI | Matplotlib | Seaborn | Scikit-learn | Data Cleaning | Feature Engineering | EDA | Data Visualization | Business Intelligence | Machine Learning | Revenue Analytics**

---

## 📌 Conclusion

This project demonstrates an end-to-end **data analytics workflow**, starting from raw NYC taxi data and progressing through data preparation, exploratory analysis, SQL querying, Power BI visualization, demand analysis, surge-pricing simulation, and machine learning.

The project focuses on converting large-scale transportation data into **actionable business insights related to demand, revenue, location performance, and pricing strategies**.
