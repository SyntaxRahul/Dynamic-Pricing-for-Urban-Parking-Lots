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
project/
│
├── data/
│   └── cleaned.csv                    # Final dataset used for pricing logic
│
├── notebooks/
│   └── dynamic_parking_pricing.ipynb # Main notebook with all models and streaming logic
│
├── outputs/
│   └── streamed_output.jsonl         # (Optional) Output from real-time Pathway stream
│
├── README.md                         # Complete project overview, models, diagram, usage
│
└── requirements.txt                  # All required Python packages (numpy, pandas, etc.)



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
