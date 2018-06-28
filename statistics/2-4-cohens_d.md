[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

The following code outputs:
```
Average weight of first babies: 7.204107733975324
Average weight of other babies: 7.301399825021872
First babies weigh 0.09729209104654846 less than later babies.

Effect size: 0.06911936019885215
```

The effect size for weight is slightly larger than for pregnancy length.  However it is still less than 1 standard deviation and therefore I do not think it is very significant.

```python
import math
import numpy as np

import nsfg
import thinkstats2
import thinkplot

def CohenEffectSize(group1, group2):
    diff = group1.mean() - group2.mean()
    
    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)
    
    pooled_var = (n1*var1 + n2*var2) / (n1 + n2)
    d = diff / math.sqrt(pooled_var)
    
    return abs(d)

def main(script):
    preg = nsfg.ReadFemPreg()
    live = preg[preg.outcome == 1]
    
    first = live[live.pregordr == 1]
    others = live[live.pregordr != 1]
    
    first_wgt = first.totalwgt_lb
    others_wgt = others.totalwgt_lb
    
    print("Average weight of first babies:", first_wgt.mean())
    print("Average weight of other babies:", others_wgt.mean())
    print("First babies weigh", others_wgt.mean()-first_wgt.mean(),
          "less than later babies.")
    
    print("\nEffect size:", CohenEffectSize(first_wgt, others_wgt))
    

if __name__ == '__main__':
    import sys
    main(*sys.argv)
```
