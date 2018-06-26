[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>> 
###  The Problem:

Investigate whether first babies are lighter or heavier than
others. Compute Cohen's d to quantify the difference. How does it compare to
the difference in pregnancy length?

###  How I solved it:
```python
import numpy as np
import nsfg
import first
import thinkstats2

#Defining variables
preg = nsfg.ReadFemPreg()
live = preg[preg.outcome == 1]
firsts = live[live.birthord == 1]
others = live[live.birthord != 1]

#Defining function for calculating Cohen's D
def CohenEffectSize(group1, group2):
    diff = group1.mean() - group2.mean()
    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)
    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / np.sqrt(pooled_var)
    return d

#Calculating mean weights for first babies and other babies 
firsts.totalwgt_lb.mean(), others.totalwgt_lb.mean()

#Output
(7.201094430437772, 7.325855614973262)

#Calculating effect size Cohen's D
CohenEffectSize(firsts.totalwgt_lb, others.totalwgt_lb)

#Output
-0.088672927072602006
```

### The Solution:

On average first babies weigh about 7.20 lbs, whereas other babies weigh about
7.33 lbs. The size of this effect as measured by Cohen's d is 0.09 standard
deviations, which is quite small. Statistically speaking, this is not large
enough to be considered a "small effect" (i.e. < 0.2) however, it is larger
than the effect size of pregnancy length (0.03) between first and other babies
seen in an earlier example.   


