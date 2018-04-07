[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>> 

## Exercise 2.4
### Setup
Used chap02ex.ipynb for the initial code. Extracted applicable code for this exercise.

~~~~~
from __future__ import print_function, division

import numpy as np

import nsfg
import first

import thinkstats2

preg = nsfg.ReadFemPreg()
live = preg[preg.outcome == 1]

firsts = live[live.birthord == 1]
others = live[live.birthord != 1]

first_hist = thinkstats2.Hist(firsts.prglngth, label='first')
other_hist = thinkstats2.Hist(others.prglngth, label='other')

def CohenEffectSize(group1, group2):
    """Computes Cohen's effect size for two groups.
    group1: Series or DataFrame
    group2: Series or DataFrame
    returns: float if the arguments are Series;
             Series if the arguments are DataFrames
    """
    
    diff = group1.mean() - group2.mean()
    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)
    
    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / np.sqrt(pooled_var)
    return d
~~~~~
    
### Solution

~~~~
firsts.totalwgt_lb.mean(), others.totalwgt_lb.mean()
CohenEffectSize(firsts.totalwgt_lb, others.totalwgt_lb)
~~~~
-0.088672927072602
~~~~~
firsts.prglngth.mean(), others.prglngth.mean()
CohenEffectSize(firsts.prglngth, others.prglngth)
~~~~~
0.028879044654449883

### Answer
Both of these Cohen's D values show a very small effect (both under 0.1). The effect on weight had a 4 times stronger than the effect on length on pregnancy but, keeping in mind the magnitude of d, it is not very significant.
