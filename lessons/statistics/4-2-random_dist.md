[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)
### Generate random numbers
import numpy as np  
random_numbers = np.random.random(1000)  

### Plot PMF
import thinkstats2  
pmf_random = thinkstats2.Pmf(random_numbers)  
thinkplot.pmf(pmf_random)  

### What goes wrong? 
#The distribution is uniform.   

### Plot CDF
cdf_random = thinkstats2.Cdf(random_numbers, label = 'random numbers')  
thinkplot.Cdf(cdf_random)  
thinkplot.Show(xlabel = None, ylabel = "CDF")  

#The distribution of CDF is not uniform  
