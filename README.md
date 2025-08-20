# Interest Rate Modeling

A Python framework for **modeling, simulating, and forecasting short-term interest rates** using **object-oriented programming (OOP)** principles.  
Implements classical one-factor models — **Vasicek, Merton, and Normal** — with modular architecture for extensibility and real-world financial applications.

---

## 📌 Highlights

- **OOP Framework:** Built around an abstract base class (`InterestRateRegressor`) with consistent interfaces for calibration, simulation, and forecasting.  
- **Multiple Models Implemented:**
  - **Vasicek Model** – mean-reverting short rate dynamics.  
  - **Merton Model** – geometric Brownian motion with drift/volatility.  
  - **Normal Model** – Gaussian short rate with direct simulation.  
- **Data-driven Calibration:** Parameters estimated from **historical CMS and CMT rates (0.25y–10y)**.  
- **Evaluation:** Comparative analysis of models using **RMSE** and graphical visualization of predicted vs. actual rates.  
- **Extensible Design:** New models can be easily integrated without changing core system architecture.  

---

## 📂 Repository Structure

```text
├── main.ipynb                  # Jupyter notebook (run pipeline end-to-end)
├── models.py                   # Model classes (Vasicek, Merton, Normal)
├── InterestRateRegressor.py    # Abstract base class (common interface)
├── ratesData.py                # Data preprocessing & management
├── utils.py                    # Helper functions
├── Data.xlsx                   # Historical CMS & CMT rate dataset
├── requirements.txt            # Python dependencies
├── Object_Oriented_Programming___II__Final_Report_.pdf  # Project report
└── README.md                   # This file
```

---

## ⚙️ Methodology

1. **Data Management**
   - Time-series CMS & CMT rates (1988–present).  
   - Cleaned, normalized, and structured for model calibration.

2. **Model Implementation**
   - **Vasicek Model:** Ornstein–Uhlenbeck mean-reverting process.  
   - **Merton Model:** Drift + volatility via geometric Brownian motion.  
   - **Normal Model:** Gaussian short-rate simulation for simplicity.  

3. **OOP Architecture**
   - `InterestRateRegressor` defines abstract methods for all models:
     - `fit()` – parameter calibration.  
     - `simulate()` – forward rate path generation.  
     - `predict()` – rate forecasting.  
   - Subclasses (`Vasicek`, `Merton`, `Normal`) override with specific implementations.

---

## 📊 Results

- **Vasicek Model** – best accuracy (lowest RMSE = **0.0070**) due to mean-reverting property.  
- **Merton Model** – robust in capturing volatility, RMSE = **0.0097**.  
- **Normal Model** – simple & efficient, but less precise (RMSE = **0.0134**).  
- Visual comparisons show Vasicek & Merton closely track actual rates, while Normal provides stable baseline approximations.  

*(See `main.ipynb` for plots and detailed outputs.)*

---

## 🚀 How to Run

1. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

2. **Run the notebook**
   ```bash
   jupyter notebook main.ipynb
   ```

3. **Workflow**
   - Load historical data from `Data.xlsx`.  
   - Calibrate Vasicek, Merton, and Normal models.  
   - Simulate and forecast rates.  
   - Compare predictions against actual rates with visual plots.

---

