[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

>> REPLACE THIS TEXT WITH YOUR RESPONSE

## Exercise 4.2
### Setup
Used chap04ex.ipynb for the initial code. Extracted applicable code for this exercise.

~~~~~
from __future__ import print_function, division

%matplotlib inline

import numpy as np

import nsfg
import first
import thinkstats2
import thinkplot
~~~~~

### Solution

~~~~
ran = np.random.random(1000)

pmf = thinkstats2.Pmf(ran)
thinkplot.Pmf(pmf, linewidth=0.1)
thinkplot.Config(xlabel='Random variate', ylabel='PMF')
~~~~

<img src="images/Screen%20Shot%202018-04-06%20at%206.34.28%20PM.png" width="400">

~~~~
cdf = thinkstats2.Cdf(ran)
thinkplot.Cdf(cdf)
thinkplot.Config(xlabel='Random variate', ylabel='CDF')
~~~~

<img src="images/Screen%20Shot%202018-04-06%20at%206.34.44%20PM.png" width="400">

### Answer
The probabilty mass function is linear with a slope of zero. The cumulative distribution function is also linear with a slope of 1. This confirms that this random number ditribution is uniform.
