[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

resp = nsfg.ReadFemResp()

hist = thinkstats2.Hist(resp.numkdhh)
print(hist)

pmf = thinkstats2.Pmf(hist, label='actual')

def BiasPmf(pmf, label):
    """
    biased distribution we would see if we surveyed the children and asked them how 
    many children under 18 (including themselves) are in their household.
    """
    new_pmf = pmf.Copy(label=label)

    for x, p in pmf.Items():
        new_pmf.Mult(x, x)
        
    new_pmf.Normalize()
    return new_pmf

#Plot the actual and biased distributions
biased_pmf = BiasPmf(pmf, label='observed')
thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf, biased_pmf])
thinkplot.Config(xlabel='Number of Children', ylabel='PMF')

# compute their means
print('Actual mean', pmf.Mean())
print('Observed mean', biased_pmf.Mean())
