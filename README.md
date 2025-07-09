# 🚗 Dynamic Pricing for Urban Parking Lots

This project implements a real-time, intelligent dynamic pricing model for 14 urban parking spaces using live data.  
Developed during **Summer Analytics 2025** organized by the **Consulting and Analytics Club, IIT Guwahati**.

---

## 📌 Project Overview

The objective is to create a smart parking pricing system using:

- **Occupancy levels**
- **Queue length**
- **Traffic congestion**
- **Vehicle type**
- **Special day/event indicator**

The solution simulates a **real-time pricing engine** using the **Pathway streaming framework**, Python, Pandas, and NumPy.

---

## 📂 Project Structure
dynamic-parking-pricing/
│
├── data/
│ └── cleaned.csv # Preprocessed dataset used in Pathway pipeline
│
├── notebooks/
│ └── dynamic_pricing_pipeline.ipynb # Main notebook with data loading, models & plots
│
├── outputs/
│ └── streamed_output.jsonl # Output of prices from real-time simulation
│
├── README.md # Project overview and documentation (this file)
└── requirements.txt # List of required packages

---

## 💻 Tech Stack

- Python 3
- Pandas & NumPy
- Pathway (for real-time streaming)
- Mermaid (for diagram)
- Bokeh (for visualization)
- Git & GitHub

---

## 🔧 How the System Works

```mermaid
flowchart TD
    A[Raw Data: dataset.csv] --> B[Preprocessing with Pandas]
    B --> C[Pathway Schema + UDFs]
    C --> D[Feature Engineering]
    D --> E[Dynamic Pricing Model]
    E --> F[JSONL Stream Output]
    F --> G[Visualization with Bokeh]
