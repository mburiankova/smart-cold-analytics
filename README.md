# smart-cold-analytics
Plateforme d'optimisation en temps réel pour réseaux de froid urbain (Bordeaux / Singapour).

# ❄️ Smart-Cold-Analytics: IoT Data Pipeline for Urban Cooling

## 🌍 The Vision
Optimizing district cooling networks (DCN) through real-time data engineering. This project aims to bridge the gap between **Bordeaux** and **Singapore** by providing a scalable infrastructure to monitor and predict energy consumption in tropical and temperate urban environments.

## 🚀 The Problem
District cooling systems often suffer from **reactive regulation**, leading to 15-20% energy waste. In high-humidity areas like Singapore, condensation management is a critical pain point.

## 🛠️ Tech Stack (The Roadmap)
This repository tracks my journey in building a production-ready data pipeline:

* **Ingestion:** Python (FastAPI / Paho-MQTT) for sensor data & OpenWeather API for localized weather.
* **Orchestration:** Apache Airflow to schedule ingestion and transformation tasks.
* **Storage:** TimescaleDB (PostgreSQL) for time-series sensor data + AWS S3 for cold storage.
* **Processing:** Pandas/PySpark for real-time Dew Point calculation and anomaly detection.
* **Visualization:** Grafana Dashboards for real-time monitoring and alerting.
* **DevOps:** Docker & Docker Compose for seamless deployment between Edge and Cloud.

## 📈 Key Features
- [ ] **Real-time Ingestion:** Connect to IoT sensors via MQTT.
- [ ] **Predictive Logic:** Anticipate cooling demand 15-30 mins ahead using weather forecasts.
- [ ] **Condensation Alerting:** Automated alerts based on real-time Dew Point analysis.
- [ ] **Multi-Region Support:** Toggle between Bordeaux (TEMPERATE) and Singapore (TROPICAL) parameters.

## 🏗️ Architecture Schema
```mermaid
graph LR
    A[IoT Sensors] --> B(MQTT Broker)
    C[Weather API] --> D(Airflow DAG)
    B --> E[Python Ingestion Service]
    D --> E
    E --> F[(TimescaleDB)]
    F --> G[Grafana Dashboard]
    E --> H[Alerting System]
