[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> REPLACE THIS TEXT WITH YOUR RESPONSE

## Exercise 5.1
### Setup
Used chap05ex.ipynb for the initial code. Extracted applicable code for this exercise.

~~~~~
from __future__ import print_function, division

%matplotlib inline

import numpy as np

import nsfg
import analytic

import thinkstats2
import thinkplot
import scipy.stats
~~~~~

### Solution

~~~~~
mu_men = 178
sigma_men = 7.7

mu_women = 163
sigma_women = 7.3

min_height_in = 5*12 + 10
max_height_in = 6*12 + 1
convert = 2.54

min_height = min_height_in * convert
max_height = max_height_in * convert

normal = scipy.stats.norm(loc=mu_men, scale=sigma_women)

low_percentile = normal.cdf(min_height)
high_percentile = normal.cdf(max_height)
percent = (high_percentile - low_percentile) * 100
~~~~~~

### Answer

~~~~
print("Percent of US male population in the range is %2d" % (percent))
~~~~~

Percent of US male population in the range is 35
