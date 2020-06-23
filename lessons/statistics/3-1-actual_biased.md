[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

from __future__ import print_function, division

%matplotlib inline

import numpy as np

import nsfg
import first
import thinkstats2
import thinkplot

def BiasPmf(pmf, label):\
    new_pmf = pmf.Copy(label=label)

    for x, p in pmf.Items():\
        new_pmf.Mult(x, x)
        
    new_pmf.Normalize()\
    return new_pmf

resp = nsfg.ReadFemResp() #resp is a pandas dataframe
resp.head()

PMF = thinkstats2.Pmf(resp.numkdhh, label='numkdhh') #unbiased

biased = BiasPmf(PMF, label='biased')

thinkplot.Pmfs([PMF, biased])
thinkplot.Config(xlabel='# of children', ylabel='PMF')

