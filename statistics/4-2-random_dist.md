[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

>> In this problem I evaluated whether 1000 randomly generated numbers from 0 to 1 result in a uniform distribution.  To solve this I created a PMF and CDF of the 1000 numbers and then graphed the results.  The 1000 numbers are close to uniformly ditributed however not exactly.  As one can see in the PMF graph, there are bands of more and lessly dense areas.  This represents areas of more and less distributions of numbers.  On the CDF graph the line is not exactly a line representing x=y, which would be a uniform distribution.  Again, it is very close but not perfect.  For practical purposes however, I think that you could consider this distribution uniform for more uses.  

![Alt Text](https://github.com/bpanzar/dsp/tree/master/statistics/4_2.png)

```python
import sys
import nsfg
import numpy as np
import thinkstats2



def main():
    rand_nums = np.random.random(1000)
    
    pmf = thinkstats2.Pmf(rand_nums, label='PMF')
    
    thinkplot.PrePlot(num=1, cols=2)
    thinkplot.Pmf(pmf, linewidth=0.1)
    thinkplot.Config(xlabel='Random variate', ylabel='PMF')
    
    cdf = thinkstats2.Cdf(rand_nums, label='CDF')
    thinkplot.SubPlot(2)
    thinkplot.Cdf(cdf)
    thinkplot.Config(xlabel='Random variate', ylabel='CDF')

if __name__ == '__main__':
    main()
```
