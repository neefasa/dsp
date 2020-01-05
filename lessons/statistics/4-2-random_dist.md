[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

## Cumulative distribution functions
The problem asked to examine the ```numpy.random.random``` function using PMF(probability mass function) and CDF(cumulative distribution function).

First I created a list of 1000 random numbers using ```numpy.random.random``` and plotted the PMF.
```python
thou_rands = [np.random.random() for i in range(1000)]
thou_pmf = thinkstats2.Pmf(thou_rands)
thinkplot.pmf(thou_pmf)
thinkplot.show(xlabel='selected random numbers', ylabel='PMF')
```
![PMF plot](https://github.com/neefasa/dsp/blob/master/lessons/statistics/thou_pmf_plot.png)
  
From first glance all points have the value of 0.001 and range from from 0 to 1.  
The range isn't surprising because the random function we are examining selects a float between 0 and 1. 
The value of 0.001 isn't surprising because I created a list of 1000 values, so each has the probablity of 0.001.
This shows that no float was selected twice, otherwise we would have had at least one value of 0.002.

The challenge with examining this plot is that we have 1000 points plotted over a small width. It would be challenging to see
if there exists a change in density over the 0 to 1 range, which would imply that the random function we are examining isn't 
truly random. Thus, I plot a CDF.

```python
thou_cdf = thinkstats2.Cdf(thou_rands)
thinkplot.cdf(thou_cdf)
thinkplot.show(xlabel='selected random numbers', ylabel='CDF')
```
![CDF plot](https://github.com/neefasa/dsp/blob/master/lessons/statistics/thou_cdf_plot.png)

The plot is basically a line with a slope of 1. This definitely points to the ```numpy.random.random``` function being truly random. 
