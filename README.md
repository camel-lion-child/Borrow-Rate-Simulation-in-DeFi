# Borrow-Rate-Simulation-in-DeFi
Simulate borrow rate changes in DeFi lending protocols (Aave-style) using Python

This project simulates how borrow rates in DeFi lending protocols like Aave change based on utilization rate. It uses a kinked interest rate model, which increases borrow rates more aggressively once utilization surpasses a certain threshold (the "kink").

* Project Goal

The goal is to visualize and understand how DeFi lending protocols dynamically adjust borrowing rates to maintain liquidity.

* Concept Overview

Base Rate: Minimum interest rate when no one is borrowing

Utilization Rate (U): Borrowed / Supplied

Slope 1: Rate of increase before optimal utilization

Slope 2: Rate of increase after optimal utilization (steeper)

Kink Point (U_opt): Utilization threshold (e.g., 80%) beyond which the interest rate rises faster

* Formula

If U <= U_opt:
    Borrow Rate = Base + Slope1 * U
Else:
    Borrow Rate = Base + Slope1 * U_opt + Slope2 * (U - U_opt)

* Parameters Used (from Aave-like setup)

Base Rate: 2%

Optimal Utilization (U_opt): 80%

Slope 1: 10%

Slope 2: 30%

* Example Calculation

Suppose:

Supplied = 1,000 USDC

Borrowed = 800 USDC

Then:

Utilization = 800 / 1000 = 80%

Borrow Rate = 2% + 10% * 0.8 = 10%

If Utilization = 95%, then:

Borrow Rate = 2% + 10% * 0.8 + 30% * (0.95 - 0.8) = 14.5%

* Chart Output

A line chart is generated showing the borrow rate increases slowly before the kink point (80%) and much more steeply after that.

🎓 Who is this for?

Data science students studying DeFi

Anyone curious about interest rate models in decentralized lending

🚀 How to Run

Clone the repo

Install Python dependencies:

pip install matplotlib pandas

Run the simulation script (Jupyter Notebook or Python script)

📄 License

MIT License - free to use for education or projects.

