# Data Binning with Pandas

Assume `price` is a feature that ranges from 5'000 to 45'500.

We would like 3 bins of equal bin-width.

```python
# Use np.linspace(l, h, n) to return n equally distant values between l and h
bins = np.linspace(min(df["price"]), max(df["price"]), 4)

groups_names = ["Low", "Medium", "High"]

# df.cut() segments and sorts data into bins
df["price-binned"] = pd.cut(df["price"], bins, labels=group_names, include_lowest=True)
```


# Dummy variables with Pandas

Convert the data frame from categorical values to quantitative ones, namely from something of this form :

| fuel   |
| ------ |
| gas    |
| diesel |
| gas    |
| gas    |

...to something of this form...

| gas | diesel |
| --- | :----: |
| 1   |   0    |
| 0   |   1    |
| 1   |   0    |
| 1   |   0    |

...by doing this :

```python
pd.get_dummies(df["fuel"])
```