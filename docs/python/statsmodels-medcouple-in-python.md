# Python 中的 statsmodels.medcouple()

> 原文:[https://www . geesforgeks . org/stats models-med couple-in-python/](https://www.geeksforgeeks.org/statsmodels-medcouple-in-python/)

借助于`**statsmodels.medcouple()**`方法，我们可以计算出时滞的 medcouple 鲁棒测度。

> **语法:** `statsmodels.medcouple(array, axis)`
> **返回:**返回 medcouple 统计值。

**例#1 :**
在这个例子中我们可以看到，通过使用`statsmodels.medcouple()`方法，我们能够通过使用这个方法来获得 medcouple 统计量的值。

```py
# import numpy and statsmodels
import numpy as np
from statsmodels.stats.stattools import medcouple

g = np.array([1, 2, 3, 4, 7, 8])
# Using statsmodels.medcouple() method
gfg = medcouple(g)

print(gfg)
```

**输出:**

> 0.2857142857142857

**例 2 :**

```py
# import numpy and statsmodels
import numpy as np
from statsmodels.stats.stattools import medcouple

g = np.array([1, 2, 8, 9, 10])
# Using statsmodels.medcouple() method
gfg = medcouple(g)

print(gfg)
```

**输出:**

> -0.5555555555555556