# Python–从数据集中移除常量特征

> 原文:[https://www . geesforgeks . org/python-从数据集中移除常量特征/](https://www.geeksforgeeks.org/python-removing-constant-features-from-the-dataset/)

数据集中包含常数值(即所有输出或目标值只有一个值)的要素称为常特征。这些功能不会向目标功能提供任何信息。这些是数据集中可用的冗余数据。此要素的存在对目标没有影响，因此最好从数据集中移除这些要素。移除冗余要素并仅保留数据集中必要要素的过程属于要素选择方法的过滤方法。

现在让我们看看如何删除 Python 中的常量特性。

**考虑文章的自建数据集:**

| 入口 | 文章类别 | 视图 |
| --- | --- | --- |
| 极客们 | 计算机编程语言 | Five hundred and forty-five |
| 极客们 | 数据科学 | One thousand five hundred and five |
| 极客们 | 数据科学 | One thousand one hundred and fifty-seven |
| 极客们 | 数据科学 | Two thousand five hundred and forty-one |
| 极客们 | 数学 | Five thousand seven hundred and twenty-six |
| 极客们 | 计算机编程语言 | Three thousand one hundred and twenty-five |
| 极客们 | 数据科学 | Three thousand one hundred and thirty-one |
| 极客们 | 数学 | Six thousand five hundred and twenty-five |
| 极客们 | 数学 | Fifteen thousand |

**编码:创建上述数据的数据框**

```py
# Import pandas to create DataFrame
import pandas as pd

# Make DataFrame of the given data
data = pd.DataFrame({"Portal":['GeeksforGeeks', 'GeeksforGeeks', 'GeeksforGeeks', 'GeeksforGeeks', 'GeeksforGeeks', 
                               'GeeksforGeeks', 'GeeksforGeeks', 'GeeksforGeeks', 'GeeksforGeeks'],
                    "Article's_category":['Python', 'Data Science', 'Data Science', 'Data Science', 'Mathematics', 
                                          'Python', 'Data Science', 'Mathematics', 'Mathematics'],
                    "Views":[545, 1505, 1157, 2541, 5726, 3125, 3131, 6525, 15000]})
```

**编码:将分类数据转换为数值数据**

```py
# import ordinal encoder from sklearn
from sklearn.preprocessing import OrdinalEncoder
ord_enc = OrdinalEncoder()

# Transform the data
data[["Portal","Article's_category"]] = ord_enc.fit_transform(data[["Portal","Article's_category"]])
```

**代码:将数据拟合到变量阈值。**

```py
# import VarianceThreshold
from sklearn.feature_selection import VarianceThreshold
var_threshold = VarianceThreshold(threshold=0)   # threshold = 0 for constant

# fit the data
var_threshold.fit(data)

# We can check the variance of different features as
print(var_threshold.variances_)
```

**输出:不同特征的方差:**

```py
[0.00000000e+00 6.17283951e-01 1.76746269e+07]
```

**编码:转换数据**

```py
print(var_threshold.transform(data))
print('*' * 10,"Separator",'*' * 10)

# shapes of data before transformed and after transformed
print("Earlier shape of data: ", data.shape)
print("Shape after transformation: ", var_threshold.transform(data).shape)
```

**输出:**

```py
[[2.000e+00 5.450e+02]
 [0.000e+00 1.505e+03]
 [0.000e+00 1.157e+03]
 [0.000e+00 2.541e+03]
 [1.000e+00 5.726e+03]
 [2.000e+00 3.125e+03]
 [0.000e+00 3.131e+03]
 [1.000e+00 6.525e+03]
 [1.000e+00 1.500e+04]]
********** Separator **********
Earlier shape of data:  (9, 3)
Shape after transformation:  (9, 2)

```

正如你之前看到的，我们有 9 个观察结果，有 3 个特征。
变换后我们有 9 个观测值，有 2 个特征。我们可以清楚地观察到，删除的功能是“门户”。