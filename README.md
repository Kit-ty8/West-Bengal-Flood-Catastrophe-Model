# West-Bengal-Flood-Catastrophe-Model

# Stochastic Catastrophe Flood Model: West Bengal Portfolio

## Project Overview
Architecting an end-to-end Property & Casualty (P&C) catastrophe model in Advanced Excel. This project simulates ground-up flood losses for a synthetic portfolio of 1,000 properties across highly exposed districts in West Bengal, bridging theoretical actuarial concepts into an automated risk engine. 


## Phase 1: Exposure Data Engineering
Generated a mathematically rigorous physical exposure dataset utilizing Excel dynamic arrays (`SEQUENCE`, `NORM.INV`, `RANDBETWEEN`). 

**Key Technical Constraints Applied:**

* **Logic-Bound Risk Combinations:** Engineered nested `IFS` statements to prevent invalid asset profiles (e.g., forcing Industrial occupancies to strictly register as 'Pucca' construction types with correlating high-end replacement values).
* **Physical Flood Vulnerability:** Incorporated variables like Plinth Height (feet) and Number of Stories to accurately model ground-level water displacement.
* **Actuarial Distribution:** Modeled Total Insured Value (TIV) using normal distributions centered around realistic replacement costs based on construction class.  

## Phase 2: Hazard Catalog & Vulnerability Matrix
Engineered the static scientific parameters required for stochastic modeling.
* **Hazard Catalog:** Hardcoded representative stochastic flood events across West Bengal, defining Return Periods, Annual Probabilities, and Max Water Depths.
* **Vulnerability Matrix:** Developed a 2D grid plotting Mean Damage Ratios (MDR). Mapped physical destruction percentages against varying flood depths and construction classes (Kutcha, Semi-Pucca, Pucca).

## Phase 3: The Calculation Engine (Simulation)
Built a dynamic simulation engine to evaluate the portfolio's Ground-Up Loss against selected disaster scenarios.
* **Effective Depth Logic:** Designed formulas to subtract individual property plinth heights from incoming floodwaters, accurately representing physical risk mitigation at the asset level.
* **2D Array Lookups:** Deployed nested `INDEX` and `MATCH` functions utilizing inline array constants (`{0,1,2,3,5,8,10}`) to bypass native Excel Table text-string limitations. This successfully executes thousands of approximate-match damage calculations instantly without workbook lag.

## Next Phase (In Development)
* **Phase 4:** Applying financial waterfalls (Deductibles, XoL Reinsurance layers) to output Average Annual Loss (AAL) and Exceedance Probability (EP) curves.
