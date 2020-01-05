[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

For this problem we examined the difference in the weight of first borns and 
non-first borns.

The mean of first borns is 7.2lb, while the mean of non-first borns is 7.3lb
The Cohen's d is 8.9%. This is about 3 times the Cohen's d for the pregnancy 
length.

```
mean_first = firsts.totalwgt_lb.mean()
mean_other = others.totalwgt_lb.mean()
cohen_d_wgt = CohenEffectSize(firsts.totalwgt_lb, 
                                 others.totalwgt_lb)
cohen_d_lngth = CohenEffectSize(firsts.prglngth, 
                                others.prglngth)

print('Mean weight of first borns:', 
      mean_first, 'lb')
print('Mean weight of non-first borns:', 
      mean_other, 'lb')
print('Difference in means', mean_other - mean_first, 'lb\n')

print("Cohen's d for weight", cohen_d_wgt)
print("Cohen's d for pregnacy length", cohen_d_lngth)
```
Mean weight of first borns: 7.201094430437772 lb  
Mean weight of non-first borns: 7.325855614973262 lb  
Difference in means 0.12476118453549034 lb  

Cohen's d for weight -0.088672927072602  
Cohen's d for pregnacy length 0.028879044654449883
