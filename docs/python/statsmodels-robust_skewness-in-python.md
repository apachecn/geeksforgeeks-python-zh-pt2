# python 中的 stats models . robust _ skew()

> 原文:[https://www . geeksforgeeks . org/stats models-robust _ skew in-python/](https://www.geeksforgeeks.org/statsmodels-robust_skewness-in-python/)

借助`**statsmodels.robust_skewness()**`方法，我们可以计算出金&白中的四个偏度测度。

> **语法:** `statsmodels.robust_skewness(array, axis)`
> **返回:**返回四个偏斜度度量值。

**示例#1 :**
在这个示例中，我们可以看到，通过使用`statsmodels.robust_skewness()`方法，我们能够使用该方法获得四个偏斜度度量的值。

```py
# import numpy and statsmodels
import numpy as np
from statsmodels.stats.stattools import robust_skewness

g = np.array([1, 2, 3, 4, 7, 8])
# Using statsmodels.robust_skewness() method
gfg = medcouple(g)

print(gfg)
```

**输出:**

> 0.2857142857142857

**例 2 :**

```py
# import numpy and statsmodels
import numpy as np
from statsmodels.stats.stattools import robust_skewness

g = np.array([1, 2, 8, 9, 10])
# Using statsmodels.robust_skewness() method
gfg = medcouple(g)

print(gfg)
```

**输出:**

> -0.5555555555555556