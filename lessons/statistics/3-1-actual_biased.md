[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

>> 
## Probablility Mass Functions
This question engages with how sampling could cause a bias in results. We use the NSFG data to similate the effect.
If we take a sample of children and ask them how many kids are in their family, larger families would be over represented.
The BiasPmf function written by the author creates a biased Pmf object simulating this. 
The following code plots two Pmfs, the one from the data from the survey and the other using the BiasPmf function.
```python
resp = nsfg.ReadFemResp()  

pmf_kids = thinkstats2.Pmf(resp.numkdhh, label='actual')  
biased_pmf_kids = BiasPmf(pmf_kids, label='biased') 

thinkplot.PrePlot(2) 
thinkplot.Pmfs([pmf_kids, biased_pmf_kids]) 
thinkplot.Show(xlabel='kids in a family', ylabel='PMF') 
```
![image of pmf](https://github.com/neefasa/dsp/blob/master/lessons/statistics/3_1_pmf.png)

### Funcation to calculate the mean of from the PMF
The following function calculates the mean from the Pmf object. 
```python
def PmfMean(pmf):  
    pmf_mean = 0 
        for x, p in pmf.Items():  
        pmf_mean += x * p 
    return pmf_mean 
    
print('Actual Mean:', PmfMean(pmf_kids)) 
print('Biased Mean:', PmfMean(biased_pmf_kids)) 
```
Actual Mean: 1.024205155043831   
Biased Mean: 2.403679100664282

As predicted larger families would be over represented if a sampling was taken amoung children. No childrenless families would be represented. As we can see from the plot of the actual data, families with no children is the most probable. 
