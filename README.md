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
  

## Next Phases (In Development)
* **Phase 2:** Building a stochastic Hazard Catalog (100+ simulated riverine, coastal surge, and flash flood events) and a granular Vulnerability Matrix (Mean Damage Ratios).
* **Phase 3:** Calculating Ground-Up Loss via exact-match lookup matrices.
* **Phase 4:** Applying financial waterfalls (Deductibles, XoL Reinsurance layers) to output Average Annual Loss (AAL) and Exceedance Probability (EP) curves.
