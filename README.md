# global-growth-ops

> Web dashboard that forecasts countries' economic growth from open World Bank data using machine learning, with automated model retraining and deployment (MLOps).

![status](https://img.shields.io/badge/status-in_development-yellow)
![license](https://img.shields.io/badge/license-MIT-green)

## 🎯 Goal

Predict GDP per capita growth for countries using macroeconomic indicators, and explain which factors drive growth the most.

**Key features:**
- Pull live data from World Bank API (free, no key required)
- Train ML model to forecast 1-year and 3-year GDP growth
- Visualize predictions + feature importance (what drives growth)
- Auto-retrain model monthly when new data arrives (MLOps pipeline)
- Deploy automatically via CI/CD to VPS with monitoring

## 📊 Data

Source: [World Bank Open Data API](https://api.worldbank.org/v2/)

### Indicators used

| Role | Indicator | Code |
|---|---|---|
| **Target** | GDP per capita growth (annual %) | `NY.GDP.PCAP.KD.ZG` |
| Feature | Government expenditure on education (% of GDP) | `SE.XPD.TOTL.GD.ZS` |
| Feature | Current health expenditure (% of GDP) | `SH.XPD.CHEX.GD.ZS` |
| Feature | Access to electricity (% of population) | `EG.ELC.ACCS.ZS` |
| Feature | Gross capital formation (% of GDP) | `NE.GDI.TOTL.ZS` |
| Feature | Exports of goods and services (% of GDP) | `NE.EXP.GNFS.ZS` |
| Feature | Real interest rate (%) | `FR.INR.RISK` |
| Feature | Energy use (kg of oil equivalent per capita) | `EG.USE.PCAP.KG.OE` |
| Feature | Urban population (% of total) | `SP.URB.TOTL.IN.ZS` |
| Feature | High-technology exports (% of manufactured exports) | `TX.VAL.TECH.MF.ZS` |
| Feature | Internet users (per 100 people) | `IT.NET.USER.P2` |

**Data coverage:** ~100 countries, 1990–2024 (panel data).

Full indicator catalog: [docs/indicators.md](docs/indicators.md)

## 🛠 Technologies

- **Language:** Python 3
- **Data / ML:** requests, pandas, scikit-learn
- **API:** FastAPI
- **Frontend:** React + Chart.js
- **Database:** PostgreSQL
- **Infrastructure:** Docker, docker-compose, Ansible, Caddy (HTTPS)
- **CI/CD:** GitHub Actions
- **Monitoring:** Prometheus, Grafana, Uptime Kuma

## 🏗 Architecture
