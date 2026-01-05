# Step-by-step reproduction guide (Aspen Plus)

This guide explains how to reproduce the Aspen Plus process model results reported in the manuscript.

## Requirements
- Aspen Plus (e.g., v12 or compatible)
- A valid Aspen license (commercial software)
- Excel (optional, for checking input/output tables)

## Files used
- Aspen model: `20241220 - Case 1 (Base)`  
- Inputs: `Input_Data/`
- Representative outputs: `Output_Results/`

## Procedure
1. Download the Aspen backup file (`.bkp`) from `Aspen_Model/`.
2. Open Aspen Plus and load the backup file.
3. Confirm the property method (e.g., Peng–Robinson) and component list.
4. Check feed composition and operating conditions:
   - Feed composition: `Input_Data/Feed_Composition.xlsx`
   - Operating conditions: `Input_Data/Operating_Conditions.xlsx`
5. Run the simulation (steady-state).
6. Compare key results with the provided outputs:
   - `Output_Results/Mass_Energy_Balance.xlsx`
   - `Output_Results/Key_Performance_Metrics.csv`

## Notes
If the Aspen file name differs, please update the filename in this document and in the main README.
