# Data Binning

Assume `price` is a feature that ranges from 5'000 to 45'500.

We would like 3 bins of equal bin-width.

```python
# Use np.linspace(l, h, n) to return n equally distant values between l and h
bins = np.linspace(min(df["price"]), max(df["price"]), 4)

groups_names = ["Low", "Medium", "High"]

# df.cut() segments and sorts data into bins
df["price-binned"] = pd.cut(df["price"], bins, labels=group_names, include_lowest=True)
```