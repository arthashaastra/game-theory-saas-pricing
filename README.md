# Game Theory - SaaS Pricing Strategy

A simulation of **Bertrand competition** between two SaaS startups, deriving Nash Equilibrium prices and visualising best-response dynamics using differentiated demand.

Built as a practical application of game theory to real startup pricing decisions.

---

## The Business Problem

When two SaaS startups compete in the same market, how should each one price its product?

Pricing in isolation — ignoring how competitors will react — is a common and costly mistake. This model treats pricing as what it actually is: a **strategic interaction** where each firm's optimal price depends on what the other charges.

---

## What This Model Does

- Models two competing SaaS firms with differentiated products
- Derives each firm's **best-response function** — the optimal price given any competitor price
- Finds the **Nash Equilibrium** — the price pair where neither firm can improve profit by changing price unilaterally
- Visualises best-response curves and the equilibrium point
- Plots Firm 1's profit landscape across all possible price combinations

---

## Key Insight

> Product differentiation raises equilibrium prices for both firms.

A startup that invests in making its product distinct (higher `c` → lower substitutability) competes less aggressively on price and earns higher margins. Differentiation is not just a marketing decision — it is a **pricing strategy**.

---

## Parameters

| Parameter | Variable | Meaning |
|-----------|----------|---------|
| Base demand | `a` | Total market demand if both firms priced at zero |
| Own-price sensitivity | `b` | How much Firm 1's demand falls when it raises its own price |
| Cross-price sensitivity | `c` | How much Firm 1's demand rises when Firm 2 raises its price |
| Marginal cost (Firm 1) | `mc1` | Minimum price Firm 1 would rationally charge |
| Marginal cost (Firm 2) | `mc2` | Minimum price Firm 2 would rationally charge |

Asymmetric costs (`mc1 ≠ mc2`) make the model more realistic — one startup may be leaner or better funded than the other, and this shifts the equilibrium in its favour.
In this model, we consider `mc1 = mc2' for simplicity and ease of understanding.

---

## Demand Structure

Firm 1's demand: `Q1 = a - b·P1 + c·P2`

Firm 2's demand: `Q2 = a - b·P2 + c·P1`

Each firm maximises profit = `(Price − Marginal Cost) × Quantity`

---

## How Nash Equilibrium is Found

Each firm's best-response function is derived by differentiating its profit function with respect to its own price and setting the derivative to zero.

The Nash Equilibrium is the simultaneous solution of both best-response functions — found numerically using `scipy.optimize.fsolve`.

---

## Sample Output

```
Nash Equilibrium Prices → Firm 1: $250.00, Firm 2: $250.00
Profit at Equilibrium  → Firm 1: $12500.00, Firm 2: $12500.00
```

---

## Extensions & Future Work

- **Collusion scenario** — what if both firms coordinated prices? How much higher would profits be, and why is this unstable?
- **Market entry simulation** — how does equilibrium shift when a third competitor enters?
- **Churn-adjusted demand** — incorporating SaaS-specific metrics like churn rate and CAC into the cost structure
- **What-if table** — equilibrium prices across a range of `c` values, showing how pricing power erodes as products become more substitutable

---

## Tools

Python · NumPy · SciPy · Matplotlib · JupyterLab

---

## About

Built by an Economics student specialising in game theory, applying equilibrium analysis to real startup strategy problems.
