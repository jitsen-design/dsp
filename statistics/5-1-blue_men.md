[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

I'd first need to import the Scipy library, as well as the stats module

```
import scipy
from scipy import stats
```

I then convert 5'10" and 6"1 to centimeters

#https://www.calculateme.com/height/convert-feet-inches-to-cm

Then, I calculate percentile values for 6'1 and 5'10

```
High_End = stats.norm.cdf(185.42, loc = 178, scale = 7.7)
Low_End = stats.norm.cdf(177.8, loc = 178, scale = 7.7)
```

Lastly, the % of the population falling between the two parameters is calculated.

```
High_End - Low_End
```
This value is at approximately 34%