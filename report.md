# From Decline to Collapse: Tracing the Drivers of Food Insecurity

## 1. Executive Summary

This report summarises a two-year longitudinal analysis of food security and its drivers across 31 European countries. By unifying datasets for national economic index, rainfall, conflict score, and food security, we identified a clear, two-tiered dynamic governing food systems: general economic decline steadily drives up food insecurity, but acute crisis precipitates absolute systemic collapse.

Our analysis reveals several critical, high-level insights into this dynamic:

- **Economy is the Dominant Channel:** Economic collapse is the dominant proximate driver of food insecurity (r = +0.92).
- **The Ripple Effects of Conflict:** Direct conflict escalation acts as a secondary driver (r = −0.45), but its most consequential pathway is indirect. Geographic proximity to conflict hotspots elevates neighboring countries' conflict scores, creating a second-order spillover that depresses economic activity and ripples through the entire food system.
- **Rainfall's Modest Role:** Rainfall has a statistically significant but economically modest direct effect (r = +0.46). It operates primarily as an agricultural input through the economy rather than as a direct shock to food access.


## 2. Dataset and Methodology

To establish a single source of truth, four datasets — national economic index, rainfall, conflict score, and food security — were merged.

- **Data Scope:** The dataset encompasses 31 countries over 732 daily timesteps, yielding 22,692 total observations.
- **Target:** 25 countries contained known food security labels; the remaining six (IDs: 0, 3, 5, 8, 11, 18) were isolated as the inference target.
- **Modeling:** We trained a Gradient Boosting regressor on the 25 labeled countries to infer the missing data. Features included normalized economy, rainfall, conflict, their interaction, and log-economy. Leave-one-country-out cross-validation confirmed robust out-of-sample generalization (CV R² = 0.893, MAE = 0.028).


## 3. The Crisis Narrative: Decline vs. Collapse

### The Baseline: Economic Decline Drives Insecurity

A country's day-to-day ability to sustain food access is tightly coupled with its economic health. Even in the absence of acute conflict, a contracting economy reliably leads to rising food insecurity levels.

- The Pearson correlation between the economy index and food security is exceptionally strong (r = +0.92).
- In our regression models, the coefficient for the normalized economy (+1.50) overwhelmingly dominates. As economic indicators slowly decline, food security degrades proportionally, highlighting economic stability as the foundational buffer against hunger.

### The Catalyst: Crisis Causes Absolute Collapse

While economic decline slowly erodes food access, acute crisis acts as the ultimate trigger that pushes the system into absolute collapse. When conflict escalates, food security does not just decline — it flatlines.

- **Pre-Crisis (Year 1):** All 31 countries operated under baseline conditions with mean food security at 0.38 ± 0.14.
- **Crisis Onset (Year 2, t ≈ 468):** Two countries experienced sharp conflict escalation. Simultaneously, nine countries recorded severe economic contractions (up to −95% drop).
- **The Flatline Effect:** In the countries hit by severe, acute crisis, food security scores effectively flatlined to near-zero. Furthermore, a stark second-order spillover effect was observed: neighboring countries experienced economic crashes due to proximity to the conflict hotspot, subsequently suffering total food security collapses despite lacking direct primary conflict.

<div align="center">
  <img src="fig_crisis_narrative.png" alt="Crisis narrative: Economic collapse precedes conflict escalation → Food insecurity" width="70%">
</div>

### The Marginal Role of Rainfall

Rainfall has a statistically significant but economically modest effect (r = +0.46).

- No acute drought signal was detectable during the two-year window.
- Rainfall likely operates through a slow agricultural channel (influencing crop yields and base GDP) rather than acting as a discrete shock to food access.

## 4. Strategic Conclusions

1. **Economic Decline Erodes Security:** Downward trends in regional economies steadily drain food access, acting as the primary proximate driver of rising, day-to-day food insecurity.
2. **Crisis Triggers Absolute Collapse:** Acute conflict pushes weakened systems over the edge, turning gradual decline into an immediate flatline where food access completely fails.
3. **Beware the Spillover:** Neighboring countries might accumulate elevated conflict exposure that suppresses their economies and, through that channel, their food security
