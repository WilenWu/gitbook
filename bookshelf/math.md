---
title: math
---

Inline math: $$\int_{-\infty}^\infty g(x) dx$$

$\int_{-\infty}^\infty g(x) dx$

Block math:

$$
\int_{-\infty}^\infty g(x) dx
$$

Or using the templating syntax:

{% math %}\int_{-\infty}^\infty g(x) dx {% endmath %}

```python
import pandas as pd
df.dropna(thresh=4)
df.dropna(axis=1, how='all')

df.fillna(method='ffill')
df.fillna(value={'A':np.mean(df.A), 'B': 1, 'C': 2, 'D': 3}, limit=1)
```
