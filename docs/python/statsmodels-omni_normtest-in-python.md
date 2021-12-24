# 状态模型。omni_normtest()用 Python

表示

> 原文:[https://www . geesforgeks . org/stats models-omni _ norm test-in-python/](https://www.geeksforgeeks.org/statsmodels-omni_normtest-in-python/)

借助于`**statsmodels.omni_normtest()**`方法，我们可以得到正态性的综合检验，并且我们使用 chi^2 分数作为这个`statsmodels.omni_normtest()`方法。

> **语法:** `statsmodels.omni_normtest(array)`
> **返回:**返回正态性综合测试。

**例#1 :**
在本例中我们可以看到，通过使用`statsmodels.omni_normtest()`方法，我们能够使用该方法中的 chi^2 分数来计算正态性的综合检验。

```py
# import numpy and statsmodels
import numpy as np
from statsmodels.stats.stattools import omni_normtest

g = np.array([1, 2, 3, 4, 5, 6, 7, 8])
# Using statsmodels.omni_normtest() method
gfg = omni_normtest(g)

print(gfg)
```

**输出:**

> NormaltestResult(统计值=1.7004056883060088，p value = 0 . 48888 . 48888888886

**例 2 :**

```py
# import numpy and statsmodels
import numpy as np
from statsmodels.stats.stattools import omni_normtest

g = np.array([1, 2, 3, 4, 5, 6, 7, 8, 9, 10])
# Using statsmodels.omni_normtest() method
gfg = omni_normtest(g)

print(gfg)
```

**输出:**

> NormaltestResult(统计值=2.02697581498966，p value = 0.02697582156