[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

>>
### The Problem:

Something like the class size paradox appears if you survey children and ask
how many children are in their family. Families with many children are more
likely to appear in your sample, and families with no children have no chance
to be in the sample.
Use the NSFG respondent variable NUMKDHH to construct
the actual distribution for the number of children under 18 in the household.
Now compute the biased distribution we would see if we surveyed the children
and asked them how many children under 18 (including themselves) are in
their household.
Plot the actual and biased distributions, and compute their
means.

### How I solved it:

```python
from __future__ import print_function, division
%matplotlib inline
import numpy as np
import nsfg
import first
import thinkstats2
import thinkplot

#Defining variables
resp = nsfg.ReadFemResp()
live = preg[preg.outcome == 1]

#Defining bias function
def BiasPmf(pmf, label):
    new_pmf = pmf.Copy(label=label)

    for x, p in pmf.Items():
        new_pmf.Mult(x, x)
        
    new_pmf.Normalize()
    return new_pmf

pmf = thinkstats2.Pmf(resp.numkdhh, label='numkdhh')
thinkplot.Pmf(pmf)
thinkplot.Config(xlabel='Number of children', ylabel='PMF')

biased = BiasPmf(pmf, label='biased')
thinkplot.PrePlot(2)

thinkplot.Pmfs([pmf, biased])
thinkplot.Config(xlabel='Number of children', ylabel='PMF')

pmf.Mean()

#Output
1.0242051550438309

biased.Mean()

#Output
2.4036791006642821
```
![alt text](https://github.com/andreasorcinelli/dsp/blob/master/img/pmf_biased_actual.png "biased vs. actual")

### The Solution:

The PMF or probability mass function for the actual distribution shows a peak
or its mode at 0 children. However, the PMF for the biased distribution shows
a peak or its mode at 2 children. Moreover, the mean of the actual distribution
is about 1.02 whereas the mean of the biased distribution is about 2.40,
reflecting a difference of about 1.38 children between the two distributions. 

