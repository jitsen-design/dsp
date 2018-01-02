[Think Stats Chapter 8 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77) (scoring)

```
# Ten separate iterations of the Standard Error:

def Multi_Sample(n,m,lam):
    RMSE_list = {}
    for x in range(10):
        RMSE_list[n+x] = RMSE(Exp_Means(n+x,m,lam), lam)

# the  plot shows that as the sample size increases, the Standard error decreases.
    thinkplot.plot([x for x in RMSE_list.keys()], [y for y in RMSE_list.values()])
    thinkplot.config(xlabel = 'Sample Size', ylabel = 'Standard Error', title = 'Standard Error v Sample Size')    

# find RMSE:

def RMSE(estimates, actual):
    e2 = [(estimate-actual)**2 for estimate in estimates]
    mse = np.mean(e2)
    return math.sqrt(mse)
    
#Find a list of means from random exponential distributions of size n

def Exp_Means(n, m, lam):
    means = []
    for _ in range(m):
        xs = np.random.exponential(1.0/lam, n)
        L = 1/np.mean(xs)
        means.append(L)
    return means

#Find the confidence interval for 1000 random samples from an exponential #distribution with lambda = 2

def CI_Exp(estimates):
    cdf = thinkstats2.Cdf(estimates)
    ci = cdf.Percentile(5), cdf.Percentile(95)
    print('confidence interval', ci)

# plot the CDF

    thinkplot.Cdf(cdf)
    thinkplot.Config(xlabel='Estimate',
                     ylabel='CDF',
                     title='Sampling distribution')
    thinkplot.show()

#Retrieve output:

print("Standard Error:",RMSE(Exp_Means(10,1000,2), 2)), 
CI_Exp(Exp_Means(10,1000,2)), Multi_Sample(10,1000,2)
```
