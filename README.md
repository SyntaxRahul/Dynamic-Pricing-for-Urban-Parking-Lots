# 🚗 Dynamic Pricing for Urban Parking Lots

This project implements a real-time, intelligent dynamic pricing model for 14 urban parking spaces using live data.  
Developed as part of **Summer Analytics 2025**, organized by the **Consulting and Analytics Club, IIT Guwahati**.

---

## 📌 Project Overview

The aim is to create a smart pricing system for parking lots by analyzing:

- Occupancy levels
- Queue lengths
- Traffic congestion
- Vehicle types
- Special event indicators

The model dynamically updates prices based on current conditions using **real-time data simulation via Pathway**, with logic built entirely from scratch using **Python, Pandas, and NumPy**.

---

## 📂 Project Structure

```
project/
│
├── data/
│   └── cleaned.csv                    # Final cleaned dataset
│
├── notebooks/
│   └── dynamic_parking_pricing.ipynb # Final notebook with pricing models and plots
│
├── outputs/
│   └── streamed_output.jsonl         # Output from the Pathway real-time stream (optional)
│
├── README.md                         # Project documentation (this file)
│
└── requirements.txt                  # Python dependencies
```

---

## 💻 Tech Stack

- Python 3
- Pandas & NumPy
- Pathway (real-time streaming)
- Bokeh (real-time visualizations)
- Mermaid (architecture diagram)
- Google Colab (development environment)
- Git & GitHub (version control & submission)

---

## 📈 Models Implemented

### ✅ Model 1: Baseline Linear Pricing
A simple model where price increases with occupancy:

```python
Price_t+1 = Price_t + α * (Occupancy / Capacity)
```

---

### ✅ Model 2: Demand-Based Pricing
Demand is calculated using multiple real-time features:

```python
Demand = α*(Occupancy/Capacity) + β*QueueLength - γ*Traffic + δ*SpecialDay + ε*VehicleTypeWeight
Price_t = BasePrice * (1 + λ * NormalizedDemand)
```

- The demand is normalized to keep prices between **0.5x and 2x** of base price.
- Vehicle types are assigned weights (e.g., car = 1, bike = 0.5, truck = 1.5)

---

### 🔁 Model 3 (Optional): Competitive Pricing
Incorporates location proximity and competitor pricing using lat-long and rerouting suggestions.

---

## 🔧 Architecture Diagram

```mermaid
flowchart TD
    A[Cleaned Data: cleaned.csv] --> B[Preprocessing with Pandas]
    B --> C[Pathway Schema & Stream Setup]
    C --> D[Feature Engineering]
    D --> E[Pricing Models (1, 2, 3)]
    E --> F[Real-Time Output (JSONL)]
    F --> G[Visualization with Bokeh]
```

---

## 📊 Visualizations

Real-time line plots (via **Bokeh**) are used to:

- Show pricing trends for each parking lot
- Compare with competitor prices (if Model 3 is implemented)

---

## 📦 Requirements

Install Python dependencies with:

```bash
pip install -r requirements.txt
```

Main libraries used:
- pandas
- numpy
- pathway
- bokeh

---

## 💡 Assumptions

- Traffic levels and special events are simulated
- Base price is $10
- Prices are restricted between $5 and $20 to prevent extreme changes

---

## 🛠 How to Run This Project

1. Open `notebooks/dynamic_pricing_pipeline.ipynb` in **Google Colab**
2. Upload `cleaned.csv` from `data/`
3. Run the notebook step-by-step
4. View the pricing updates and visualizations
5. (Optional) Save the output as `streamed_output.jsonl`

---

## 🎓 Acknowledgements

Thanks to the **Consulting & Analytics Club, IIT Guwahati** and **Pathway** for organizing Summer Analytics 2025 and supporting this real-time analytics project.
