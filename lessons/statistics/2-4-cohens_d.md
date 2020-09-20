[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

### Compute the Cohen effect size for this difference. 

def CohenEffectSize(group1, group2):
    """Computes Cohen's effect size for two groups.
    
    group1: Series or DataFrame
    group2: Series or DataFrame
    
    returns: float if the arguments are Series;
             Series if the arguments are DataFrames
    """
    diff = group1.mean() - group2.mean()

    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)

    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / np.sqrt(pooled_var)
    return d
    
d =CohenEffectSize(firsts.totalwgt_lb, others.totalwgt_lb)
print('Cohen d', d)

### How does it compare with the difference in pregnancy length for first babies and others?

'''
For total weight, 'firsts' are 0.088 sd smaller than 'others'. Nevertheless,
for pregnancy length 'firsts' present a longer pregancy than 'others' by 0.078 sd.

'''
