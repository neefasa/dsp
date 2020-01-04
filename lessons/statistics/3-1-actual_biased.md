[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

>> 
resp = nsfg.ReadFemResp()

pmf_kids = thinkstats2.Pmf(resp.numkdhh, label='actual')
biased_pmf_kids = BiasPmf(pmf_kids, label='biased')
thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf_kids, biased_pmf_kids])
thinkplot.Show(xlabel='kids in a family', ylabel='PMF')



def PmfMean(pmf):
    pmf_mean = 0
    for x, p in pmf.Items():
        pmf_mean += x * p
    return pmf_mean

print('Actual Mean:', PmfMean(pmf_kids))
print('Biased Mean:', PmfMean(biased_pmf_kids))
Actual Mean: 1.024205155043831
Biased Mean: 2.403679100664282
