# Algorithms and calculation logic

This document describes the algorithmic logic implemented in the Aspen Plus process model.

## Overall workflow
1. Define feed composition and operating conditions.
2. Simulate reaction performance in the reactor block.
3. Perform downstream separation and recycle/purge handling
4. Close mass and energy balances for the entire process.
5. Report key performance indicators (KPIs) such as conversion, selectivity, yields, and utilities.

## Reactor model logic
- Reactor type: RStoic (stoichiometric reactor).
- The reactor performance is defined by specifying fixed stoichiometric reactions
  and component-wise conversion fractions rather than intrinsic reaction kinetics.
- Methane conversion is imposed based on experimentally or literature-derived values.
- Product distributions (e.g., C2H4, H2, and minor by-products) are determined by
  predefined stoichiometric relationships and specified split fractions.
- This approach enables direct mapping of experimentally observed conversion and
  selectivity to process-level mass and energy balances.

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
