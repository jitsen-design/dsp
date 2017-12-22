[Think Stats Chapter 2 Exercise 4](http://greenteapress.com/thinkstats2/html/thinkstats2003.html#toc24) (Cohen's d)

>>I first create relevant lists for the analysis, filtering and capturing weight and length of pregnancy variables for first-born children and others, respectively.

```
preg = nsfg.ReadFemPreg()
live = preg[preg.outcome == 1]
firsts_wgt = firsts.totalwgt_lb[live.birthord == 1]
others_wgt = others.totalwgt_lb[live.birthord != 1]
firsts_prg = firsts.prglngth[live.birthord == 1]
others_prg = others.prglngth[live.birthord != 1]
```

Next, we calculate Cohen's d for the first=borns and others on two variables: weight and length of pregnancy.

```
def CohenEffectSize(group1, group2):
    diff = group1.mean() - group2.mean()

    var1 = group1.var()
    var2 = group2.var()
    n1, n2 = len(group1), len(group2)

    pooled_var = (n1 * var1 + n2 * var2) / (n1 + n2)
    d = diff / math.sqrt(pooled_var)
    return d
    ```

```
CohenEffectSize(firsts_wgt, others_wgt), CohenEffectSize(firsts_prg, others_prg)
```

Cohen's d for weight is -.0887, which means that the average first-borns weigh less than 53.5% of others.

Cohen's d for pregnancy length is .0289, which means that first-borns have an average pregnancy length that is greater than for 51.2% of others.

We can also plot the differences to show the discrepancies visually. We can use Probability Mass Functions to show relative likelihoods of weight and pregnancy length for both groups.

```
firsts_prg_pmf = thinkstats2.Pmf(firsts_prg, label = 'Firsts')
others_prg_pmf = thinkstats2.Pmf(others_prg, label = 'Others')

fig = thinkplot.figure(figsize=(20,5))
thinkplot.SubPlot(2, cols=2);
thinkplot.Pmfs([firsts_prg_pmf, others_prg_pmf]);
thinkplot.Show(xlabel='weeks', axis=[27, 46, 0, 0.6]);
```

```
firsts_wgt_pmf = thinkstats2.Pmf(firsts_wgt, label = 'firsts')
others_wgt_pmf = thinkstats2.Pmf(others_wgt, label = 'others')

fig = thinkplot.figure(figsize=(30,10));
thinkplot.SubPlot(2, cols=2);
thinkplot.Pmfs([firsts_wgt_pmf, others_wgt_pmf]);
thinkplot.Show(xlabel='weight', ylabel = 'probability', axis=[2, 12, 0, 0.04]);
```




