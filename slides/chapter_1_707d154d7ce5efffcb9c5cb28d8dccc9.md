---
title: Insert title here
key: 707d154d7ce5efffcb9c5cb28d8dccc9

---
## Cumulative distribution functions

```yaml
type: "TitleSlide"
key: "4c7ca13c60"
```

`@lower_third`

name: Allen Downey
title: Professor, Olin College


`@script`
Script


---
## From PMF to CDF

```yaml
type: "FullSlide"
key: "5e1d3af58b"
```

`@part1`
PMF: Probability Mass Function

CDF: Cumulative Distribution Function

If you draw a random element from a distribution:

* PMF tells you the probability that you get exactly x,

* CDF tells you the probability that you get a value <= x

for a given value of x.


`@script`



---
## Example

```yaml
type: "FullSlide"
key: "df82e8d6f2"
```

`@part1`
If the distribution has 5 elements, {1, 2, 2, 3, 5}

PMF(1) = ⅕  .....  CDF(1) = ⅕

PMF(2) = ⅖   .....   CDF(2) = ⅗ 

PMF(3) = ⅕   .....    CDF(3) = ⅘

PMF(5) = ⅕  .....    CDF(5) = 1

The CDF is the cumulative sum of the PMF.


`@script`



---
## Make and plot a CDF

```yaml
type: "FullCodeSlide"
key: "322ac3909c"
```

`@part1`
```python
gss = pd.read_hdf('data/GSS.HDF')
cdf = Cdf.from_seq(gss.age)
cdf.plot()
decorate(xlabel='Age', ylabel='CDF')
```
![](image-url)


`@script`



---
## Final Slide

```yaml
type: "FinalSlide"
key: "27c0083e6b"
```

`@script`


