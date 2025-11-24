# EDS 222 Final Project:

## Herbarium Maple Specimens and Leaf Coloration Timing

### Hypothesis:

The effect of day of year (DOY) on the probability of Maple leaf specimen coloration changed over time, with a steeper relationship between DOY and coloration probability after a specific year breakpoint.

### Model description: segmented model

``` math
\begin{align}
\text{BinaryOutcome} &\sim \text{Binomial}(1, p) \\
\text{logit}\bigl(P(\text{BinaryOutcome} = 1)\bigr) &=
\begin{cases}
\beta_0 + \beta_1 \cdot \text{DOY} + \beta_2 \cdot \text{MeanFall}, & \text{if } \text{Year} \le \psi \\[2mm]
\beta_0 + \beta_1' \cdot \text{DOY} + \beta_2 \cdot \text{MeanFall}, & \text{if } \text{Year} > \psi
\end{cases}
\end{align}
```

-   **Response family:** binomial (Y=1 indicated a colored leaf herbarium specimen, Y=0 is not colored)
-   **Link function:** logit
-   **Predictors:** day of year (DOY), mean fall temperature (Mean_Fall), Year (segmented predictor)

#### Statistical hypothesis:

-   **Null hypothesis (H0):** One slope describes the effect of DOY on leaf coloration (slopes are the same before and after breakpoint)

H0: $\beta_1 = \beta_1'$

-   **Alternative hypothesis (Ha):** Multiple slopes describe the effect of DOY on leaf coloration (slopes are different before and after breakpoint)

Ha: $\beta_1 \neq \beta_1'$
