[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

>> To solve this problem I had to find what percentage of the U.S. male population in within the range from 5'10" and 6'1".  To do this I created a normal distribution using the mean and standard deviation parameters supplied by the author.  I then converted the range to centimeters.  Using this range I found two percentile ranks from a CDF made from the normal distribution and subtracted the difference between these percentile ranks.  The result is 34.27%.

```python
import scipy.stats

mu = 178
sigma = 7.7

dist_male_hgt = scipy.stats.norm(loc=mu, scale=sigma)

hgt_upper = (6*12 + 1) * 2.54
hgt_lower = (5*12 + 10) * 2.54

percent_upper = dist_male_hgt.cdf(hgt_upper)
percent_lower = dist_male_hgt.cdf(hgt_lower)

percent_diff = (percent_upper - percent_lower)*100

print('{0:.2f}%'.format(percent_diff))
```
