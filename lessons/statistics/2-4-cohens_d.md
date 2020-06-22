[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>> **The difference between the first baby's weight and other's baby's weight is about 0.08 standard deviations, which is extremely an extremely difference. The difference between the first baby's preganancy legnth and other babies' pregnancy length is about 0.02 standard deviations, which is also small. To put it into perspective, the difference between men and women is about 1.7 standard deviations.**

>> **from __future__ import print_function, division\

%matplotlib inline\

import numpy as np\

import thinkstats2\
import nsfg\
import first\
from collections import Counter\
import thinkplot\

preg = nsfg.ReadFemPreg()
live = preg[preg.outcome == 1]
#live.head()

firsts = live[live.birthord == 1]
others = live[live.birthord != 1]

  def CohenEffectSize(group1, group2):
      #Computes Cohen's effect size for two groups.
    
   group1: Series or DataFrame
   #group2: Series or DataFrame
    
   #returns: float if the arguments are Series;
            #Series if the arguments are DataFrames
    #"""
   diff = group1.mean() - group2.mean()

   var1 = group1.var()
   var2 = group2.var()
   n1, n2 = len(group1), len(group2)

   pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
   sigma = np.sqrt(pooled_var)
   #d = diff / np.sqrt(pooled_var)
   d = diff / sigma
   return d
    
#Computer CohenEffectSize between first baby's and other baby's weight
first_weight = firsts.totalwgt_lb
others_weight = others.totalwgt_lb

print(CohenEffectSize(first_weight, others_weight))
#type(first_weight) 

#Computer CohenEffectSize between first baby's and other baby's weight
first_prglngth = firsts.prglngth
others_prglngth = others.prglngth

print(CohenEffectSize(first_prglngth, others_prglngth))**
