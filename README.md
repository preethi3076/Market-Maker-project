# Market-Maker-project 
# Intraday Market-Making Simulator

## Objective
A rule-based liquidity provision engine built in Python to simulate market-making mechanics on energy futures (`CL=F`). The project focuses on managing inventory risk and mitigating adverse selection.

## Core Mechanics
* **Dynamic Quoting:** Generates synthetic bid/ask spreads anchored to the market mid-price.
* **Inventory Skewing:** Implements Avellaneda-Stoikov style logic to automatically adjust quote levels based on current inventory (e.g., lowering bids when long inventory is too high to flatten exposure).
* **Risk Controls:** Enforces hard position limits (±10 lots) and a rolling-volatility 'kill-switch' to automatically halt quoting during rapid market shocks.

## Performance & PnL Decomposition
The simulation tracks and separates total returns into two distinct components to evaluate true market-making edge:
1. **Earned Spread PnL:** Profit generated strictly from capturing the bid/ask spread.
2. **Mark-to-Market (MTM) Risk:** Unrealized losses/gains from holding directional inventory during price swings.

*Data Note: Due to the paywalls surrounding institutional L2 tick data, this simulation utilizes 5-minute OHLCV data as a structural proxy to test the core risk-management logic.*
