# SA EV Charging Economics

Analysis of electric vehicle charging costs in South Africa, comparing the BYD Dolphin Surf against petrol vehicles.

---

## Project Overview

A colleague asked me: *"Should I buy the BYD Dolphin Surf?"*

I analysed 1,193 charging sessions and calculated real costs using South African rates to answer this question with data.

**Answer:** Yes - you'll save R15,550 per year on fuel costs alone.

---

## Key Findings

**Monthly Fuel Costs (Cape Town Commuter: 60km/day)**
- EV charging: R615/month
- Petrol equivalent: R1,911/month
- **Monthly savings: R1,296**

**5-Year Total Cost**
- BYD Dolphin (purchase + charging): R377,000
- Petrol car (purchase + fuel): R465,000
- **5-year savings: R88,000**

**Charging Strategy Matters**
- 100% home charging: R506/month
- 80% home, 20% public: R615/month
- 100% public charging: R1,073/month
- All options still beat petrol (R1,911/month)

---

## Project Structure

```
sa-ev-charging-economics/
│
├── 01_EV_Analysis.py                          # Data cleaning script
├── 02_Feature_Engineering_SA_Analysis.ipynb     # Cost calculations
├── 03_Visualizations.ipynb             # Charts and graphs
│
├── ev_charging_patterns.csv                     # Original dataset
├── ev_charging_patterns_CLEAN.csv               # Cleaned data
├── ev_charging_patterns_WITH_FEATURES.csv       # With SA cost calculations
│
├── chart1_monthly_scenarios.png                 # Monthly cost comparison
├── chart2_5year_tco.png                         # 5-year total cost
├── chart3_charging_strategy.png                 # Charging mix impact
│
├── README.md                                    # This file
└── requirements.txt                             # Python dependencies
```

---

## How to Run This Analysis

### Prerequisites
- Python 3.8 or higher
- Jupyter Notebook

### Installation

1. Clone this repository:
```bash
git clone https://github.com/yourusername/sa-ev-charging-economics.git
cd sa-ev-charging-economics
```

2. Install required packages:
```bash
pip install -r requirements.txt
```

3. Run the notebooks in order:
```bash
jupyter notebook
```

Open and run:
1. `02_Feature_Engineering_SA_Analysis.ipynb`
2. `03_Visualizations.ipynb`

---

## Data Sources

**EV Charging Dataset**
- Source: [Kaggle - EV Charging Patterns](https://www.kaggle.com/)](https://www.kaggle.com/datasets/valakhorasani/electric-vehicle-charging-patterns)
- Contains 1,320 charging sessions from US cities
- Used to analyse cost patterns, then translated to SA context

**South African Pricing (December 2024)**
- **GridCars DC Fast Charging:** R7.35/kWh ([GridCars Tariffs](https://www.gridcars.com/))
- **GridCars AC Charging:** R5.88/kWh ([GridCars Tariffs](https://www.gridcars.com/))
- **Eskom Home Charging:** R3.00/kWh (average residential rate)
- **Petrol Price:** R21/liter (December 2024)
- **BYD Dolphin Surf:** R339,900 (Standard model, 30.08 kWh battery, 232 km range)

---

## Methodology

### 1. Data Cleaning
- Removed duplicate and corrupted rows
- Handled missing values with flags
- Standardised charger type labels
- Result: 1,193 usable charging sessions

### 2. Feature Engineering
- Calculated efficiency metrics (km/kWh, cost/km)
- Applied South African charging rates
- Compared EV costs to petrol equivalent
- Created annual cost scenarios for different user types

### 3. Key Assumption
Used **BYD Dolphin Surf specifications** for cost calculations:
- Real-world efficiency: 7.71 km/kWh (232 km range / 30.08 kWh battery)
- More accurate than dataset averages (which were unrealistically low)

### 4. Visualization
Created three charts showing:
- Monthly costs by user type
- 5-year total cost of ownership
- Impact of charging strategy on costs

---

## Technologies Used

- **Python 3.12** - Data analysis
- **Pandas** - Data manipulation
- **Matplotlib** - Visualizations
- **Seaborn** - Chart styling
- **Jupyter Notebook** - Interactive analysis

---

## Important Notes

### What This Analysis DOES Include
- Fuel/charging costs based on SA rates
- Purchase prices (cash, list price)
- Real-world BYD Dolphin Surf efficiency

### What This Analysis DOES NOT Include
- Financing costs (interest on loans)
- Insurance differences
- Maintenance costs
- Depreciation
- Trade-in values

**For a complete financial picture, factor in your specific financing terms and trade-in value before making a purchase decision.**

---

## Dataset Limitations

The original dataset had some quality issues:
- Charging durations didn't match charger type expectations (all ~2.3 hours)
- Vehicle efficiency values were lower than real-world modern EVs

For accurate SA projections, I supplemented with:
- BYD Dolphin Surf manufacturer specifications
- GridCars infrastructure data
- Eskom residential rates

This demonstrates the importance of validating data against ground truth sources.

---

## Results Summary

**For a typical Cape Town commuter (60km/day, 22 work days/month):**

| Metric | EV (BYD Dolphin) | Petrol Car | Savings |
|--------|------------------|------------|---------|
| Monthly fuel cost | R615 | R1,911 | R1,296 |
| Annual fuel cost | R7,380 | R22,932 | R15,552 |
| 5-year total cost | R377,000 | R465,000 | R88,000 |

**Recommendation:** Even with occasional public charging, EVs offer significant cost savings in South Africa.

---

## Contact

Questions or feedback? Feel free to open an issue or reach out!

---

## License

This project is open source and available under the MIT License.

---

## Acknowledgments

- Kaggle community for the EV charging dataset
- GridCars for public charging infrastructure data
- BYD for vehicle specifications
