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
In a previous lesson we saw the probability mass function, or PMF, which tells you -- if you draw a random value from a distribution -- what's the chance of getting x, for any give value of x.

In this lesson, we'll start working with the cumulative distribution function, or CDF, which tells you the change of getting a value less than or equal to x.


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
As an example, suppose the distribution only has 5 elements, 1, 2, 2, 3, and 5.

The PMF says that the probability of value 1 is 1/5; the probability of value 2 is 2/5, and the probabilities for 3 and 5 are 1/5.

The CDF is the cumulative sum of the probabilities from the PMF.

For example, the CDF of 2 is three fifths, because three out of 5 values in the distribution are less than or equal to 2.

The CDF of 5 is 1, or 100%, because all of the values in the distribution are less than or equal to 5.


---
## Make and plot a CDF

```yaml
type: "FullCodeSlide"
key: "322ac3909c"
center_content: true
```

`@part1`
```python
gss = pd.read_hdf('data/GSS.HDF')
cdf = Cdf.from_seq(gss.age)
cdf.plot()
decorate(xlabel='Age', ylabel='CDF')
```
![CDF of ages in GSS](https://assets.datacamp.com/production/repositories/3500/datasets/1ef32a8450fd93a8069f1aca0c4fd692bda76369/chap2lesson1fig1.png)


`@script`
The `eda` library provides a `Cdf` object which is similar to the `Pmf` object we've seen.

It provides the `from_seq` function, which takes any kind of sequence and returns a new Cdf object.

In this case, the sequence is the Series `gss.age`, from the GSS dataset.  So this is the distribution of ages for the respondents in the General Social Survey.

The x-axis is the ages, from 18 to 89.

The y-axis is the cumulative probabilities, from 0 to 1.


---
## Evaluating the CDF

```yaml
type: "TwoColumns"
key: "5f158e9604"
```

`@part1`
```python
q = 51
p = cdf(q)
0.66
```


`@part2`
![Example showing the forward interpretation of the CDF](https://assets.datacamp.com/production/repositories/3500/datasets/6e80f6a33fcd8f2bac27bbdec07f5e7158ab19ea/chap2lesson1fig2.png)


`@script`
The cumulative distribution function is actually a function, so if you give it an age, it returns the corresponding probability.

In this example, the age is the quantity, `q`, which is 51.

The corresponding probability is `p`, which is 0.66.

That means that about 66% of the respondents are 51 years old or younger.

The arrow in the figure shows how you could read this value off the CDF, at least approximately.


---
## Evaluating the inverse CDF

```yaml
type: "TwoColumns"
key: "a61436a1b4"
```

`@part1`
```python
p = 0.25
q = cdf.inverse(p)
30

p = 0.75
q = cdf.inverse(p)
57
```


`@part2`
![Example showing the inverse interpretation of the CDF](https://assets.datacamp.com/production/repositories/3500/datasets/19d39541bddf4848c836f797a51c634353e1959c/chap2lesson1fig3.png)


`@script`
The CDF is not just a function; it's an invertible function, which means that if you have a probability, `p`, you can look up the corresponding quantity, `q`.

In this example, I look up the probability 0.25, which returns 30.  That means that 25% of the respondents are age 30 or less.

Another way to say the same thing is "age 30 is the 25th percentile of this distribution".

I also look up probability 0.75, which returns 57, so 75% of the respondents are 57 or younger.

Or you could sat that the 75th percentile of this distribution is age 57.

Again, the arrows in the figure show how you could read these values off the graph.

By the way, the distance from the 25th to the 75th percentile is called the interquartile range, or IQR.  It measures the spread of the distribution, so it is similar to standard deviation or variance.  Because it is based on percentiles, it doesn't get thrown off by extreme values or outliers, the way variance does.  So IQR can be more "robust" than variance, which means it works well even if there are errors in the data or extreme values.


---
## Final Slide

```yaml
type: "FinalSlide"
key: "27c0083e6b"
```

`@script`
Is this an outro, or am I supposed to replace it?

