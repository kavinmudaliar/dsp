[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

 **We can see that the distribution is uniform because the cumulative distribution function has a constant slope. This what we would expect for a uniform probability density function. **

from __future__ import print_function, division

%matplotlib inline

import numpy as np

import nsfg
import first
import thinkstats2
import thinkplot

random_numbers = np.random.random(1000)

pmf = thinkstats2.Pmf(random_numbers)
thinkplot.Pmf(pmf, linewidth=0.1)
thinkplot.Config(xlabel='Random values', ylabel='PMF')

cdf = thinkstats2.Cdf(random_numbers)
thinkplot.Cdf(cdf)
thinkplot.Config(xlabel='Random variate', ylabel='CDF')

