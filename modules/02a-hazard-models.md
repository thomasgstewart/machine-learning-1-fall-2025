# Hazards models

## A

If you have not yet completed part D from 01b, please complete it.

## B

Let $T$ be time to failure for laptop batteries.  Suppose there are two battery manufacturers, A and B.  Suppose the distribution for time to battery failure for units produced by A is gamma,

$$
T|A \sim \text{GAMMA(rate = 5, shape = 12)}
$$

Also suppose the log relative hazard of batteries from group B compared to group A is 0.5.  That is

$$
\log \frac{h(t|B)}{h(t|A)} = 0.5 
$$

Generate a dataset of 100 draws from $T|A$ and $T|B$ (for a total of 200 draws).  Compare the empirical distribution of the draws to the theoretical distribution.  (There are several options: PDF overlaid on histogram, CDF overlaid on eCDF, QQ-plot, etc.)

| Time of battery failure | Manufacturers |
|:---:|:---:|
| 2.3 | A |
| 2.1 | B |
| 3.3 | A |
| ... | ...|

HINT: [Inverse CDF sampling (link)](https://en.wikipedia.org/wiki/Inverse_transform_sampling) may be helpful.

## C

Repeat part B under the assumption that 

$$
\log \frac{h(t|B)}{h(t|A)} = 0.7 - 0.1t
$$