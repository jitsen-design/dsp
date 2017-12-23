[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

>> 
First, I create a PMF for the houseold size based on exising data

```
resp = nsfg.ReadFemResp()
household_pmf = thinkstats2.Pmf(resp.numkdhh, label = 'Household Kids')
```

I then create a function for a biased PMF by squaring each response and creating a new normalized PMF

```
def BiasPmf(pmf):
	new_pmf = pmf.Copy(label= 'Biased Household Kids')
	for x, p in pmf.Items():
       	new_pmf.Mult(x, x)
        
    new_pmf.Normalize()
    return new_pmf
```

I can then plot and compare the two PMFs

```
fig = thinkplot.figure(figsize=(15,5));
thinkplot.SubPlot(2, cols = 2);
thinkplot.Pmfs([household_pmf, bias_pmf]);
thinkplot.Show(xlabel='Number of Children', ylabel = 'Probability', axis=[0, 6, 0, 0.6]);
```
The PMFs show a distinct spike in household size within the biased sample, as expected.