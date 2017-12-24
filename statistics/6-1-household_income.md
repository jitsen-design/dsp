[Think Stats Chapter 6 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2007.html#toc60) (household income)

We first need to import libraries and modules for this exercise
```
import thinkstats2
import thinkplot
import hinc
import numpy as np
%matplotlib inline
```

I then find log values for the upper and lower bounds for each of the data ranges, assuming 3 for the lowest value, and 6 for the highest.
```
income_table = hinc.ReadData()
income_table['log_upper'] = np.log10(income_table.income)
income_table['log_lower'] = income_table.log_upper.shift(1)
income_table.loc[0, 'log_lower'] = 3.0
income_table.loc[41, 'log_upper'] = 6.0
```

I then find random n values between each set of bounds; n being the frequency of each range. Having done that, I append each random value to a fresh list.
```
list_of_lists = []
for x,y in income_table.iterrows():
    array = np.linspace(y.log_lower, y.log_upper, y.freq)
    list_of_lists.append(array)
log_income_dist = np.concatenate(list_of_lists)
```

I can then plot the CDF for the sample of random log values .
```
income_dist_cdf = thinkstats2.Cdf(log_income_dist, label = 'Log Income CDF')
thinkplot.Cdf(income_dist_cdf)
thinkplot.Show(xlabel='Log of Sample Income', ylabel='CDF')
```

Actual income will be the inverse of the log values, so I plot those as well.
```
actual_income = [10**(x) for x in log_income_dist]
actual_income_cdf = thinkstats2.Cdf(actual_income, label = 'Income CDF')
thinkplot.Cdf(actual_income_cdf)
thinkplot.Show(xlabel='Sample Income', ylabel='CDF')
```

I can then find the mean, median and standard deviation for the sample.
```
std = np.std(actual_income)
mean = np.mean(actual_income)
median = np.median(actual_income)

mean, std, median
```

Further, I find the skewness as well as Pearson's skeweness for the data.
```
skewness = sum((((x-mean)/std)**3) for x in actual_income)/len(actual_income)
Pearson_skewness = 3 * (mean - median) / std

skewness, Pearson_skewness
```

Finally, I can infer what proportion of the sample report taxable income below the mean.
```
thinkstats2.Cdf(actual_income).Prob(mean)
