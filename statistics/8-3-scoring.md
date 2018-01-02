[Think Stats Chapter 8 Exercise 3](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77)

---

```
def time_differential(lam):
    time_between_goals = np.random.exponential(1/lam)
    goals = 0
    t = 0
    while True:
        t += time_between_goals
        goals += 1
        if t > 1:
            break
    return goals
            

def multi_sample_2(lam, m):
    sample_list = []
    for i in range(m):
        x = time_differential(lam)
        sample_list.append(x)
    thinkplot.plot([x for x in range(m)], sample_list)
    thinkplot.show()
    print('rmse of Samples:', RMSE(sample_list, lam))
    
            
time_differential(2), multi_sample_2(2, 10)

---