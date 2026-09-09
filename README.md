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
* **Vulnerability Matrix:** Structured a 2D Mean Damage Ratio (MDR) lookup grid. Quantified physical destruction percentages at specific intersections of varying flood depths and construction classes (Kutcha, Semi-Pucca, Pucca).

## Phase 3: The Calculation Engine (Simulation)
Built a dynamic simulation engine to evaluate the portfolio's Ground-Up Loss against selected disaster scenarios.
* **Effective Depth Logic:** Designed formulas to subtract individual property plinth heights from incoming floodwaters, accurately representing physical risk mitigation at the asset level.
* **2D Array Lookups:** Deployed nested `INDEX` and `MATCH` functions utilizing inline array constants (`{0,1,2,3,5,8,10}`) to bypass native Excel Table text-string limitations. This successfully executes thousands of approximate-match damage calculations instantly without workbook lag.

Phase 4: Financial Structuring & Executive Dashboarding
The final phase of this project transitions physical Ground-Up Loss into realized financial liability through policy and treaty-level structures, culminating in an executive-level actuarial dashboard.

Reinsurance Engine (Excess of Loss)
Asset-Level Deductibles: Applied a 5% Total Insured Value (TIV) deductible to all properties. Utilized MAX(0, Ground_Up - Deductible) logic to ensure payouts are bound by a logical zero-floor.

Treaty Application: Built a dynamic, portfolio-level Reinsurance recovery module. Implemented nested MIN/MAX logic to automatically calculate Reinsurance Recovery and Net Retained Loss against specific thresholds:

Primary Retention: ₹5,00,00,000

Treaty Limit: ₹20,00,00,000

Multi-Event Matrix & Simulation
What-If Analysis: Engineered an automated multi-event matrix using Excel Data Tables to bypass manual scenario toggling. The matrix forces the calculation engine to run all 8 flood scenarios (FL_001 to FL_008) simultaneously, logging the Gross Loss for each of the 6 districts.

Quality Control: Implemented strict floor constraints (MAX) on the NORM.INV statistical generation to prevent extreme left-tail distributions from creating negative TIV anomalies and breaking the downstream financial calculations.

Actuarial Visualization
The model concludes with a dynamic, presentation-ready dashboard designed for pricing and risk executives:

Portfolio Gross Loss by Disaster Scenario: A stacked column chart grouping absolute financial destruction by event, color-coded by the geographically impacted district to prove spatial isolation logic.

Net Retained Loss EP Curve: An Exceedance Probability curve utilizing LARGE array ranking and empirical probability formulas (Rank / N+1). The visual perfectly demonstrates the financial flattening effect of the ₹5 Crore primary retention cap during high-frequency attritional events.
