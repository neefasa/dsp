[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

The question asked to find what percentage of men would be able to join the Blue Man Group. The height range is 5'10" and 6'1". Height is roughly normal with mu = 178cm and sigma = 7.7cm for men. 

```python
import scipy.stats

# First convert units from foot-inch to cm
upper_height = (6*12+1)*2.54
lower_height = (5*12+10)*2.54

#Mean of male height is 178cm and standard deviation is 7.7cm
mu = 178
sigma = 7.7
male_height_dist = scipy.stats.norm(loc=mu, scale=sigma)

#Calculate the percentiles of the BMG height limits
upper_perc = male_height_dist.cdf(upper_height)
lower_perc = male_height_dist.cdf(lower_height)

print('%.1f%% of men qualify for BMG' % ((upper_perc-lower_perc)*100))
```
34.3% of men qualify for BMG
