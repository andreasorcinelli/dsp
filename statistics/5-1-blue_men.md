[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> 
### The Problem:

In the BRFSS (see Section 5.4), the distribution of heights is roughly normal
with parameters μ = 178 cm and σ = 7.7 cm for men, and μ = 163 cm and σ = 7.3
cm for women.

In order to join Blue Man Group, you have to be male between 5’10” and 6’1”
(see http://bluemancasting.com). What percentage of the U.S. male population
is in this range?

### How I solved it:
```python

import numpy as np
import nsfg
import first
import analytic
import thinkstats2
import thinkplot
import scipy.stats

mu = 178
sigma = 7.7
dist = scipy.stats.norm(loc=mu, scale=sigma)
type(dist)
dist.mean(), dist.std()
dist.cdf(mu-sigma)

low = dist.cdf(177.8)    # 5'10"
high = dist.cdf(185.4)   # 6'1"
low, high, high-low

#Output
(0.48963902786483265, 0.83173371081078573, 0.34209468294595308)
```

### The Solution:

Given that height in males is normally distributed with a mean of 178 cm and a
standard deviation of 7.7 cm, I used the cumulative distribution function (or
CDF; a function that maps from values to their cumulative probabilities) to find
the percentage of males who fall between 5'10" and 6'1", the height requirements
to be in the Blue Man Group. Approximately 34 % of males fall within this range. 

