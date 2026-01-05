# Algorithms and calculation logic

This document describes the algorithmic logic implemented in the Aspen Plus process model.

## Overall workflow
1. Define feed composition and operating conditions.
2. Simulate reaction performance in the reactor block.
3. Perform downstream separation and recycle/purge handling (if applicable).
4. Close mass and energy balances for the entire process.
5. Report key performance indicators (KPIs) such as conversion, selectivity, yields, and utilities.

## Reactor model logic
- Reactor type: RPlug (plug-flow reactor) or equivalent block (update if different).
- Conversion/selectivity implementation:
  - Methane conversion is specified as a function of temperature and/or residence time.
  - Product distribution is calculated based on fitted selectivity correlations or lumped kinetics.
- Stoichiometry and lumping:
  - CH4 is converted to C2 products (e.g., C2H4) and H2.
  - Any side products (e.g., C2H6, C3+, aromatics, coke/char proxy) are represented via lumped components if used.

## Heat and utility calculations
- Heat duties are computed by Aspen from stream enthalpies and block energy balances.
- Furnace/electric heater duties (if present) are reported as utilities.
- If an electrified unit is assumed, electricity demand is obtained from the corresponding heat duty.

## Reported outputs
- Stream tables (flows, compositions, temperatures, pressures)
- Block duties (reactor, heat exchangers, compressors, etc.)
- Overall KPIs:
  - CH4 conversion
  - C2 selectivity
  - C2 yield
  - Net electricity/heat demand
