# Python - Pandas

## What you actually need to know about pandas (skip the 200-page docs)

read_csv(), read_json() - loading data

.head(), .info(), .describe() - what you're looking at

Indexing: df[col], df.loc[], df.iloc[], df[df['col'] > value]
.groupby(), .agg() - grouping and summarizing

.merge(), .join() - combining datasets

.fillna(), .dropna(), .astype() - cleaning
.apply() - transform columns

That's genuinely it. You'll learn the rest by doing.

## Python file structure

1. python -m venv venv
   - if vsc asks "We noticed a new environment has been created. Do you want to select it for the workspace folder?" - select yes - this will use venv packages instead of system packages.
     - if you miss this prompt you can still set the venv folder by:
       - Press Ctrl+Shift+P (or Cmd+Shift+P on Mac)
       - Select "Python: Select Interpreter"
       - Choose your venv from the list (should show something like ./venv/bin/python)

2. YOU MUST ACTIVATE THE NEW VENV - cmd `source venv/Scripts/activate`

3. Now when you run `pip install`, it installs into *that* venv, not system-wide.
   - Then to install everything at once:```pip install -r requirements.txt```
   - Check with cmd `jupyter notebook`
   - If not working:  ```pip install jupyter pandas numpy requests matplotlib seaborn```
   - Then cmd: `jupyter notebook`

## NumPy: Raw numerical computing, blazingly fast math on arrays

- Everything is a numpy array (n-dimensional grid of numbers)
- Fast vectorized operations: array * 2 multiplies every element instantly
- Linear algebra, statistics, random numbers
- Foundation layer—pandas is built on top of numpy

```import numpy as np
arr = np.array([1, 2, 3, 4, 5])
arr * 2  # [2, 4, 6, 8, 10] - fast
np.mean(arr)  # statistics
```

## Pandas: User-friendly data manipulation on labeled tables

- Works with DataFrames (like Excel sheets or SQL tables with column names)
- Each column can be different types (one column is dates, another is strings, another is numbers)
- Built for messy real-world data: missing values, merging tables, grouping, reshaping
- Easy to load CSV/JSON, filter rows, rename columns

```import pandas as pd
df = pd.DataFrame({
    'name': ['Alice', 'Bob', 'Charlie'],
    'age': [25, 30, 35],
    'salary': [50000, 60000, 75000]
})
df[df['age'] > 26]  # filter by condition
df.groupby('age')['salary'].mean()  # group and aggregate
```
