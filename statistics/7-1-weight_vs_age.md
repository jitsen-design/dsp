[Think Stats Chapter 7 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2008.html#toc70) (weight vs. age)

Scatter plot for birthweights and age at pregnancy:
```
preg = nsfg.ReadFemPreg()
live = preg[preg.outcome == 1]
live2 = live.dropna(subset = ['agepreg', 'totalwgt_lb'])
scatter = thinkplot.Scatter(live.agepreg, live.totalwgt_lb, alpha = 0.025)
thinkplot.Show(xlabel = "Mother's Age", ylabel = 'Total Weight')
```

Line graph of percentiles of birthweights against age at pregnancy:
```
cdf_totalwgt_lb = thinkstats2.Cdf(live.totalwgt_lb)
weights = [cdf_totalwgt_lb.PercentileRank(x) for x in live.totalwgt_lb]
agepreg_new, weights_new = zip(*sorted(zip(live.agepreg, weights)))
plt.plot(agepreg_new, weights_new)
fig = thinkplot.figure(figsize=(30,20))
thinkplot.show
```
The line graph shows a very even distribution.

Correlation between the two variables:
```
age = np.array(agepreg_new)
weight = np.array(weights_new)
cov = np.dot(age-np.mean(age), weight-np.mean(weight)) / len(weight)
corr = cov / np.sqrt(np.var(age)*np.var(weight))
print("Correlation:",corr)
```

Spearman's Corrlelation between the two variables:
```
def SpearmanCorr(xs, ys):
    xs = pandas.Series(xs)
    ys = pandas.Series(ys)
    return xs.corr(ys, method='spearman')

print("Spearman's Correlation:",SpearmanCorr(age, weight))
```

There seems to be a very weak correlation between birthweight and age of mothers during pregnancy.
