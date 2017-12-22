[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

>> I first generate a random list
```
random_list = [random.randint(0,1000) for p in range(0,10001)]
```

Next, I find the PMF as as well as CDF functions; and plot their graphs.

```
random_list_pmf = thinkstats2.Pmf(random_list, label = 'Random Number Prob')
thinkplot.Hist(random_list_pmf)
thinkplot.Show(xlabel='Number', ylabel='Probability')
```

```
random_list_cdf = thinkstats2.Cdf(random_list, label = 'Random Number Prob')
thinkplot.Cdf(random_list_cdf)
thinkplot.Show(xlabel='Number', ylabel='Probability')
```
The even distribution of the PMF and the linear nature of the CDF tells us that the probabilities of each value occuring in a random list are equal.
