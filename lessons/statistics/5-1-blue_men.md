[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

from __future__ import print_function, division

%matplotlib inline

import numpy as np

import nsfg
import first
import analytic

import thinkstats2
import thinkplot
import scipy.stats

avg = 178 #average height [cm]
std_dev = 7.7 #standard deviation [cm]
dist = scipy.stats.norm(loc=avg, scale=std_dev)

lower_bound = 177.8 # 5'10 lower height in cm\
upper_bound = 185.4 # 6'1  upper height in cm\
answer = dist.cdf(upper_bound) - dist.cdf(lower_bound)\
print('Percentage of United States male population between the height of 5\'10 and 6\'1:', answer)

