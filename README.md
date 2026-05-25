# 🚲 Citi Bike NYC Transit Analysis

> **Can bike-sharing fill the gaps in NYC's subway network?**
> We crunched the data to find out.

[![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)](https://python.org)
[![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-150458?logo=pandas)](https://pandas.pydata.org)
[![Status](https://img.shields.io/badge/Status-Complete-brightgreen)](https://github.com/ppyaethu1504/citibike-nyc-transit-analysis)

---

## 📌 Overview

This project combines **real-time Citi Bike station data** with **MTA subway stop locations** to study NYC's bike-sharing and transit infrastructure. Using geodesic distance calculations and availability metrics, we surface insights about accessibility gaps and underserved communities across NYC's boroughs.

---

## ❓ Research Questions

1. Which Citi Bike stations are nearest to MTA subway stations?
2. Which neighborhoods depend most on Citi Bike when transit is unavailable?
3. How many Citi Bike stations near subways suffer from low bike availability?
4. Which subway stops require a 5+ minute walk to the nearest Citi Bike station?
5. Which neighborhoods are underserved by **both** subway and Citi Bike?

---

## 🗂️ Data Sources

- **[CityBikes API](https://api.citybik.es/v2/)** — Real-time Citi Bike station data (availability, capacity, coordinates)
- **[Transitland API](https://www.transit.land/documentation/rest-api/stops)** — MTA subway stop locations via `f-dr5r-nyctsubway` feed

---

## 🔬 Methodology

- Fetched live data from the CityBikes API for the `citi-bike-nyc` network
- Retrieved 400 MTA subway stops via the Transitland REST API
- Computed geodesic distances between every Citi Bike station and subway stop using `geopy`
- Classified stations into NYC areas based on coordinates (Manhattan, Brooklyn, Queens, Bronx/Upper Manhattan)

### 📏 Key Thresholds

- 🔴 **High Dependency** — Citi Bike station > 1.0 km from nearest subway
- 🟡 **Low Availability** — < 20% bikes available relative to station capacity
- 🚶 **Poor Walk Access** — Nearest Citi Bike > 0.4 km (~5 min walk) from subway
- ⚠️ **Underserved** — Station is BOTH > 1.0 km from subway AND < 20% availability

---

## 🛠️ Tech Stack

`Python` · `Pandas` · `GeoPy` · `Matplotlib` · `Jupyter Notebook`

---

## 🚀 How to Run

```bash
# 1. Clone the repo
git clone https://github.com/ppyaethu1504/citibike-nyc-transit-analysis.git
cd citibike-nyc-transit-analysis

# 2. Install dependencies
pip install requests pandas geopy matplotlib

# 3. Add your Transitland API key where API_KEY is set in the notebook

# 4. Run the notebook top to bottom
```

---

## 👥 Team

- **Sone Phyo** — [@ppyaethu1504](https://github.com/ppyaethu1504)
- **Teammate** — [@username](https://github.com/username)

