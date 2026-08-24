# SaaS Growth & Product Strategy Analysis

## Project Overview

This project was completed as part of a Master's in Data Insights & Analytics capstone using data from **Optima Life**, a fictional Software-as-a-Service (SaaS) company in the digital health and wellness industry.

The capstone was designed as a consulting-style business challenge: use customer, subscription, product, and engagement data to determine how the company could reignite growth and position its product portfolio for its next phase of expansion.

**Tools:** SQL | Snowflake | Python | Pandas | Matplotlib  
**Analysis Period:** 2019–2024  
**Project Type:** Team Capstone — Growth Strategy & Product Portfolio workstreams shown here were my contribution

---

## The Company

Optima Life is a fictional digital health and wellness subscription company founded in 2018.

The company operates five subscription products:

| Product | Description | Launch |
|---|---|---|
| Healthy Meals | Meal planning and nutrition guidance | 2018 |
| Daily Fitness | Personalized workout and activity tracking | 2019 |
| Wellness Tracker | Holistic health monitoring | 2020 |
| Mindful Living | Mental wellness and mindfulness | 2020 |
| Premium Health | Integrated health management service | 2022 |

Following strong early growth, Optima Life experienced significant expansion during 2020 and 2021 as consumer interest in digital health increased during the pandemic.

By 2023, however, growth had slowed and the company was missing its growth targets.

### The Business Challenge

Leadership needed a data-backed strategy to answer a broader question:

> **How should Optima Life reignite growth and position the company for its next phase of expansion?**

The full team capstone examined four strategic areas:

- Growth strategy
- Customer acquisition
- Churn and retention
- Product portfolio performance

My contribution focused on **Growth Strategy** and **Product Portfolio Strategy**.

---

# 1. Growth Strategy

## Business Question

> **Should Optima Life focus more resources on acquiring new customers or extracting additional value from its existing subscriber base?**

Rather than assuming one growth lever was superior, I analyzed how the company's sources of ARR growth had evolved and whether customers who expanded their relationship with Optima Life demonstrated greater long-term value.

## Approach

The analysis examined:

- New ARR vs. Expansion ARR over time
- The changing contribution of expansion to positive ARR growth
- Product-level acquisition and expansion patterns
- Retention and customer value for expanded vs. non-expanded customers
- Whether differences persisted after controlling for customer tenure

SQL was used in Snowflake to construct customer- and product-level SaaS metrics, while Python was used for analysis and visualization.

---

## Key Finding 1: Acquisition Remained the Largest Growth Source, but Its Momentum Weakened

New ARR remained the company's largest source of positive growth, but acquisition peaked in 2021 and declined afterward.

At the same time, Expansion ARR became an increasingly meaningful contributor to growth.

Expansion ARR increased from approximately **1.5% of positive ARR growth in 2019 to 16.3% in 2023**.

This suggested that relying primarily on new customer acquisition was becoming less sustainable and that the existing customer base represented a growing opportunity.

---

## Key Finding 2: Expanded Customers Demonstrated Stronger Retention

To determine whether expansion was simply generating additional short-term revenue or was associated with stronger customer relationships, I compared customers who expanded with customers who did not.

Among customers with comparable tenure:

| Customer Group | Avg. Active Years | Churn Rate |
|---|---:|---:|
| Expanded Customers | 4.15 | 14.2% |
| Non-Expanded Customers | 3.17 | 41.2% |

Expanded customers stayed active longer and experienced substantially lower churn.

The relationship also persisted after controlling for tenure, strengthening the case that expansion was associated with higher long-term customer value rather than simply reflecting older customer relationships.

---

## Growth Strategy Recommendation

Optima Life should **maintain customer acquisition while shifting greater emphasis toward retention and expansion**.

Recommended actions:

1. **Maintain targeted acquisition** rather than pursuing broad acquisition equally across every product.
2. **Increase investment in retention and customer expansion**, using cross-sell, upgrades, and targeted offers to deepen existing customer relationships.
3. **Use engagement and retention interventions to create expansion opportunities**, rather than treating retention and revenue growth as separate strategies.

The objective is not to replace acquisition. New customers remain necessary to replenish the customer base.

Instead, the analysis supports a more balanced growth model in which Optima Life acquires selectively while extracting greater long-term value from customers it already has.

---

# 2. Product Portfolio Strategy

## Business Question

> **Which products show the strongest engagement, renewal rates, and growth potential, and which products require changes in positioning, investment, or scope?**

A single portfolio-wide strategy would overlook important differences between products.

I therefore evaluated each product using three primary dimensions:

- **ARR Growth** — financial trajectory
- **Renewal Rate** — customer retention
- **Average Customer Sessions** — engagement

I also analyzed co-subscription behavior to determine whether weaker products should be dropped, repositioned, or bundled with stronger products.

---

## Portfolio Findings

The analysis revealed meaningful differences across the five products.

### Premium Health — Growth Leader

- **28.0% ARR growth**, the strongest in the portfolio
- 66.0% renewal rate
- 47.0 average sessions, the lowest engagement in the portfolio

Premium Health demonstrated strong growth potential, but its weaker engagement and retention suggested that growth should be supported by stronger onboarding, adoption, and retention efforts.

### Healthy Meals — Retention Anchor

- **78.1% renewal rate**, the highest in the portfolio
- **63.9 average sessions**, the highest engagement
- Slight ARR decline

Healthy Meals remained a dependable core product despite slower growth, making it a strong candidate for retention and cross-selling strategies.

### Daily Fitness — Strongest Balanced Performer

- 3.2% ARR growth
- 77.8% renewal
- 63.2 average sessions

Daily Fitness combined positive growth with strong renewal and engagement, supporting continued investment and expansion.

### Wellness Tracker — Reposition

Wellness Tracker showed declining ARR and below-median renewal performance.

However, a large share of its customers also subscribed to other Optima Life products, meaning immediate removal could put broader customer relationships at risk.

### Mindful Living — Highest-Priority Turnaround Candidate

Mindful Living recorded:

- **-12.7% ARR growth**, the weakest in the portfolio
- **62.1% renewal**, also the lowest

Its performance justified a deeper review of positioning and scope, but co-subscription behavior suggested that immediately dropping the product could affect valuable multi-product customers.

---

## Portfolio Recommendation

The analysis did **not** support managing all five products with the same strategy.

Instead, I recommended differentiated actions:

| Product | Recommended Strategy |
|---|---|
| Daily Fitness | Prioritize investment and expansion |
| Premium Health | Continue growth while strengthening adoption and retention |
| Healthy Meals | Protect as a core retention and cross-sell product |
| Wellness Tracker | Reposition and test bundling before reducing scope |
| Mindful Living | Prioritize turnaround and evaluate consolidation |

For the weaker products, the recommended first step was to test **bundling or feature consolidation with Premium Health** before considering removal.

This led to a:

> **Bundle first → evaluate results → drop only if the pilot fails**

strategy.

---

# Final Business Recommendation

The two analyses point toward the same broader strategy:

### Move from a primarily acquisition-led growth model toward differentiated, customer-value-led growth.

Optima Life should:

- Maintain targeted acquisition where product-level growth potential remains strong
- Increase investment in retaining and expanding existing customers
- Use high-retention products as cross-sell anchors
- Strengthen engagement before aggressively scaling high-growth products
- Reposition or consolidate weaker products before considering removal
- Manage each product according to its individual growth, retention, and engagement profile

The analysis demonstrates that sustainable growth is not simply a question of acquiring more customers. It requires understanding **which customers create long-term value, which products deserve investment, and where retention and expansion can strengthen the portfolio.**

---

# Technical Approach

### SQL & Snowflake

SQL was used to:

- Calculate customer- and product-level ARR
- Separate New ARR and Expansion ARR
- Calculate renewal and retention metrics
- Compare expanded and non-expanded customers
- Evaluate product-level growth
- Identify co-subscription behavior
- Analyze customer relationships across the product portfolio

### Python

Python was used to:

- Transform Snowflake query outputs for analysis
- Compare customer groups
- Build portfolio-level metrics
- Visualize growth and retention patterns
- Create the product portfolio positioning framework

