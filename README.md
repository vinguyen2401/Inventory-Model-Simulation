# Inventory Optimization Using Simulation

## Problem Overview
A hardware store faces challenges in maintaining optimal stock levels for electric drills due to variable daily demand and lead time. The store incurs the following costs:

- **Fixed Order Cost**: $20 per order
- **Holding Cost**: $0.02 per drill per day
- **Stockout Cost**: $8 per unsatisfied demand

The objective is to minimize the total monthly cost by finding the best combination of **Order Quantity (Q)** and **Reorder Point (R)**.

![Inventory Management Simulation](https://github.com/vinguyen2401/Inventory-Model-Simulation/raw/main/Inventory%20management.jpg)

### Data Summary
- **Demand distribution**:
  - Demand = 0: Probability = 0.05
  - Demand = 1: Probability = 0.10
  - Demand = 2: Probability = 0.20
  - Demand = 3: Probability = 0.40
  - Demand = 4: Probability = 0.15
  - Demand = 5: Probability = 0.10

- **Lead time distribution**: Uniform between 1 and 3 days.

## Approach
We used a Monte Carlo simulation to model daily demand and lead time uncertainty. The goal was to evaluate various combinations of **Q** and **R** and identify the combination that minimizes the total cost.

### Simulation Parameters
- **Initial Stock**: 7 drills
- **Fixed Order Cost**: $20 per order
- **Holding Cost**: $0.02 per drill/day
- **Stockout Cost**: $8 per unsatisfied demand
- **Timeframe**: 25 days per month

### Step-by-Step Process
1. Simulate daily demand and calculate stock levels.
2. Reorder when stock drops below the reorder point (R).
3. Calculate:
   - **Ordering cost** if reordering is triggered
   - **Holding cost** based on daily stock levels
   - **Stockout cost** for unmet demand
4. Compare total monthly costs for each (Q, R) combination.

### Scenario Manager Results
The table below shows the results of different combinations of **Q** and **R** based on total costs, broken down into **Holding Cost**, **Stockout Cost**, and **Order Cost**:

| **Scenario** | **Order Quantity (Q)** | **Reorder Point (R)** | **Holding Cost ($)** | **Stockout Cost ($)** | **Order Cost ($)** | **Total Cost ($)** |
|--------------|------------------------|-----------------------|----------------------|-----------------------|--------------------|-------------------|
| Q8R5         | 8                      | 5                     | $1.78                | $97.08                | $120.90            | $219.84           |
| Q8R8         | 8                      | 8                     | $1.41                | $114.56               | $146.00            | $259.52           |
| Q10R5        | 10                     | 5                     | $2.36                | $140.24               | $174.90            | $317.62           |
| Q10R8        | 10                     | 8                     | $1.78                | $96.12                | $121.50            | $222.57           |
| Q12R5        | 12                     | 5                     | $2.60                | $111.76               | $137.50            | $256.17           |
| Q12R8        | 12                     | 8                     | $2.21                | $83.96                | $105.30            | $190.93           |
| Q14R5        | 14                     | 5                     | $3.05                | $95.28                | $120.90            | **$217.72**       |
| Q14R8        | 14                     | 8                     | $2.69                | $75.92                | $94.80             | **$172.93**       |

### Optimal Scenario: Q14R8
From the simulation results, the **Q14R8** scenario was identified as the best solution, with the lowest total cost of **$172.93**. This combination ensures minimal stockout and holding costs while maintaining a manageable ordering frequency.

## Final Result
![Scenario Summary](https://github.com/vinguyen2401/Inventory-Model-Simulation/raw/main/Scenario%20Summary.png)

## Conclusion
By applying Monte Carlo simulation and scenario analysis, we identified the **Q14R8** combination as the most cost-effective solution for managing electric drill inventory. This scenario balances holding, stockout, and ordering costs to achieve optimal inventory levels.

## Skills Demonstrated
- **Monte Carlo Simulation**
- **Scenario Analysis using Excel**
- **Inventory Optimization Techniques**
- **Cost Minimization in Variable Demand Environments**
