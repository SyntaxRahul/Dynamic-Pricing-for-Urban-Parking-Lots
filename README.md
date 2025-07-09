# 🚗 Dynamic Pricing for Urban Parking Lots

This project implements a real-time, intelligent dynamic pricing model for 14 urban parking spaces using live data.  
Developed as part of **Summer Analytics 2025**, organized by the **Consulting and Analytics Club, IIT Guwahati**.

---

## 📌 Project Overview

The goal of this project is to build a smart, data-driven pricing system for parking lots using:

- Occupancy levels
- Queue lengths
- Traffic congestion
- Vehicle types
- Special event indicators

The pricing logic dynamically updates in real time using **Pathway**, with all models built from scratch using **NumPy** and **Pandas**.

---

## 📂 Project Structure

```
project/
│
├── data/
│   └── cleaned.csv                     # Final cleaned dataset
│
├── notebooks/
│   └── dynamic_parking_pricing.ipynb  # Final notebook with models and logic
│
├── outputs/
│   └── streamed_output.jsonl           # Optional: Pathway real-time output
│
├── README.md                           # This documentation file
│
└── requirements.txt                    # Required Python packages
```

---

## 💻 Tech Stack

- Python 3
- Pandas & NumPy
- Pathway (for real-time streaming)
- Bokeh (for visualization)
- Mermaid (for architecture diagram)
- Google Colab (development environment)
- Git & GitHub (version control)

---

## 📈 Models Implemented

### ✅ Model 1: Baseline Linear Pricing

```python
Price_t+1 = Price_t + α * (Occupancy / Capacity)
```

A simple reference model that increases price as occupancy increases.

---

### ✅ Model 2: Demand-Based Pricing

```python
Demand = α*(Occupancy/Capacity) + β*QueueLength - γ*Traffic + δ*SpecialDay + ε*VehicleTypeWeight
Normalized_Demand = (Demand - min) / (max - min)
Price_t = BasePrice * (1 + λ * Normalized_Demand)
```

Price is adjusted based on real-time demand, ensuring bounded fluctuations (0.5x to 2x base price).

---

### 🔁 Model 3 (Optional): Competitive Pricing

- Incorporates location-based competition
- Suggests rerouting when lots are full
- Adjusts pricing based on proximity and availability of nearby lots

---

## 🔧 Architecture Diagram

```mermaid
flowchart TD
    A[Cleaned Data: cleaned.csv] --> B[Preprocessing with Pandas]
    B --> C[Pathway Schema and Stream Setup]
    C --> D[Feature Engineering]
    D --> E[Pricing Models]
    E --> F[Real-Time Output (JSONL)]
    F --> G[Visualization with Bokeh]
```

---

## 📊 Visualizations

- Line charts to show pricing trends for each parking lot
- Bokeh is used to generate real-time visualizations
- Comparisons with competitor prices (if Model 3 is used)

---

## 📦 Requirements

Install dependencies with:

```bash
pip install -r requirements.txt
```

Main libraries:
- pandas
- numpy
- pathway
- bokeh

---

## 💡 Assumptions

- Vehicle types are assigned weights (e.g., car = 1.0, bike = 0.5, truck = 1.5)
- Base price = $10
- Prices are bounded between $5 and $20
- Traffic and event data are simulated

---

## 🛠 How to Run

1. Open `notebooks/dynamic_pricing_pipeline.ipynb` in Google Colab
2. Upload the dataset from `data/cleaned.csv`
3. Run all cells step-by-step
4. View price updates and visualizations
5. (Optional) Save results as `streamed_output.jsonl`

---

## 🎓 Acknowledgements

Special thanks to the **Consulting & Analytics Club, IIT Guwahati** and **Pathway**  
for organizing Summer Analytics 2025 and supporting this real-time analytics project.
