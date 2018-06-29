[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

>> The problem is to determine the probability mass function of children under 18 in the respondents' households and then to determine the PMF as observed by the children themselves.  To solve this problem I selected the numdhh column in the respondents DataFrame supplied by nsfg.ReadFemResp().  I then created a pmf using thinkstats2.pmf and a biased pmf using the appropriate calclation (multiplying each probability by the number of children in that category).  I then plotted the histogram and called the Mean function to calculate the mean.

```python

from __future__ import print_function, division

import nsfg
import thinkstats2
import thinkplot


def BiasPmf(pmf, label_):
    new_pmf = pmf.Copy(label=label_)
    
    for x, p in new_pmf.Items():
        new_pmf.Mult(x, x)
        
    new_pmf.Normalize()
    return new_pmf

def main():
    resp = nsfg.ReadFemResp()
    children_under18 = resp.numkdhh
    
    pmf_actual = thinkstats2.Pmf(children_under18, label='actual')
    pmf_biased = BiasPmf(pmf_actual, 'observed')
    
    thinkplot.PrePlot(2)
    thinkplot.Pmfs([pmf_actual, pmf_biased])
    thinkplot.config(xlabel='Children under 18', ylabel='PMF')
    
    print("Actual mean of children under 18:",
          pmf_actual.Mean())
    print("Observed mean of children under 18:",
          pmf_biased.Mean())   

if __name__ == '__main__':
    main()
```
