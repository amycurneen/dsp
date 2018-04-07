[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

>>

## Exercise 3.1
### Setup
Used chap03ex.ipynb for the initial code. Extracted applicable code for this exercise.

~~~~
from __future__ import print_function, division

%matplotlib inline

import numpy as np

import nsfg
import first
import thinkstats2
import thinkplot

preg = nsfg.ReadFemPreg()
live = preg[preg.outcome == 1]

def BiasPmf(pmf, label):
    new_pmf = pmf.Copy(label=label)

    for x, p in pmf.Items():
        new_pmf.Mult(x, x)
    new_pmf.Normalize()
    return new_pmf

def UnbiasPmf(pmf, label=None):
    new_pmf = pmf.Copy(label=label)

    for x, p in pmf.Items():
        new_pmf[x] *= 1/x
    new_pmf.Normalize()
    return new_pmf
~~~~~

### Solution

~~~~~
resp = nsfg.ReadFemResp()
pmf = thinkstats2.Pmf(resp.numkdhh, label='numkdhh')

biased_pmf = BiasPmf(pmf, label='biased')
thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf, biased_pmf])
thinkplot.Config(xlabel='numkdhh', ylabel='PMF')

print('Actual mean', pmf.Mean())
print('Biased mean', biased_pmf.Mean())
~~~~~

<img src="images/Screen%20Shot%202018-04-06%20at%2010.51.28%20AM.png" width="400">

Actual mean 1.024205155043831

Biased mean 2.403679100664282

### Answer

