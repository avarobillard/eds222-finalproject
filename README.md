# EDS 222 Final Project:

## Herbarium Maple Specimens and Leaf Coloration Timing

### Hypothesis:

The effect of year on the probability of Maple leaf specimen coloration changed over time, with a steeper relationship between year and coloration probability after a specific year breakpoint.

### Model description: segmented model

$$
\text{BinaryOutcome} \sim \text{Binomial}(1, p)
$$

$$
\text{logit}(p) =
\beta_0 + \beta_1 \cdot \text{doy} + \beta_2 \cdot \text{year} + \beta_3 \cdot \text{year} \cdot \text{after} + \beta_4 \cdot \text{meanfall}
$$

$$
\text{after}=
\begin{cases}
0 & \text{if year} \le \psi \\
1 & \text{if year} > \psi
\end{cases}
$$

-   **Response family:** binomial (Y=1 indicated a colored leaf herbarium specimen, Y=0 is not colored)
-   **Link function:** logit
-   **Predictors:** day of year (doy), mean fall temperature (mean_fall), year (segmented predictor)

#### Statistical hypothesis:

-   **Null hypothesis (H0):** One slope describes the effect of year on leaf coloration (slopes are the same before and after breakpoint)

H0: $\beta_3 = 0$

-   **Alternative hypothesis (Ha):** Multiple slopes describe the effect of year on leaf coloration (slopes are different before and after breakpoint)

Ha: $\beta_3 \neq 0$
