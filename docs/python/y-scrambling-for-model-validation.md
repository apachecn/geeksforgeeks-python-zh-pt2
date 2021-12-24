# 模型验证的 Y 置乱

> 原文:[https://www . geesforgeks . org/y-模型验证加扰/](https://www.geeksforgeeks.org/y-scrambling-for-model-validation/)

y 置乱是一种可以用来测试模型所做的预测是否只是偶然的方法。它用于多元线性回归 QSPR 模型的验证。它有许多名字 Y-置乱，Y-随机化，Y-置换等。这个过程执行起来非常简单，我们将详细了解它。

#### 置乱的步骤:

Y-Scrambling 背后的直觉很简单，首先你在原始数据上训练你的模型，并记录它的性能指标。接下来要做的是对目标列进行洗牌，以便正确的特征-目标对现在被新的不正确的特征-目标对替换。现在，您需要在这些数据上训练您的模型，并记下它的性能指标。您可以重新调整目标列并重复这些步骤。我们期望的是，该模型在原始数据上表现良好，而在混合数据上表现不佳。如果情况不是这样，并且度量标准变化不大，那么这意味着预测不可靠。逐步过程如下:-

1.  Train the model on the original feature-target pair.
2.  Pay attention to the performance index.
3.  Until a certain number of iterations are repeated.
    *   Shuffle the target column.
    *   Train the model on the new feature-target pair.
    *   Pay attention to performance indicators.
4.  Analyze the indexes of the original pair and the mixed pair.

#### 实现 Y 置乱:

在本教程中，我将使用 sklearn 的数据集模块中的波士顿房价数据集，该数据集将返回一个字典，其中特征将出现在**数据**键下，目标出现在**目标**键下。让我们从导入数据开始:-

```
import numpy as np
from sklearn.datasets import load_boston

data = load_boston()
X = data.data
Y = data.target
```

现在我们有了特性和目标，让我们执行 Y 置乱的前两个步骤，即训练模型并记录性能指标。

```
from sklearn.linear_model import LinearRegression
from sklearn.metrics import r2_score

reg = LinearRegression()
reg.fit(X,Y)

ypred = reg.predict(X)
original_r2 = r2_score(Y,ypred)
print(original_r2)
```

原来 _r2 出来是 **0.74064。**至此，我们已经完成了前两个步骤。现在我们将进行下一步，即洗牌目标阵列，训练模型，并在循环中存储性能指标。这些步骤必须重复一定次数的迭代，在本教程中，我把这个次数视为 100 次。需要注意的一点是

```
shuffled_r2 = []
from tqdm.notebook import trange
for i in trange(100):
    np.random.shuffle(Y)

    reg = LinearRegression()
    reg.fit(X,Y)

    ypred = reg.predict(X)
    shuffled_r2.append(r2_score(Y,ypred))
```

如果你打印 shuffled _ r2，你会看到这个模型表现糟糕。shuffled_r2 的前几个值如下:-

```
>>> shuffled_r2[:20]
[0.015336761335013271,
 0.0176654793204013,
 0.01740534118134418,
 0.02319807700450416,
 0.018487786525668626,
 0.02251746334707183,
 0.03766952947632973,
 0.01854475963361435,
 0.03570134149232318,
 0.022607830815118635,
 0.016603896471999002,
 0.0386838401376941,
 0.024355424374905343,
 0.04058673452547956,
 0.014581835385169217,
 0.03193842111822809,
 0.03366492627548756,
 0.02274120932669821,
 0.04335824299249236,
 0.02665799106621214]
```

### 代码:

## 蟒蛇 3

```
import numpy as np
from sklearn.datasets import load_boston
from sklearn.linear_model import LinearRegression
from sklearn.metrics import r2_score

# LOADING THE DATA
data = load_boston()
X = data.data
Y = data.target

#TRAINING OVER ORIGINAL TARGET
reg = LinearRegression()
reg.fit(X,Y)

ypred = reg.predict(X)
original_r2 = r2_score(Y,ypred)
print(original_r2)

# TRAINING OVER SHUFFLED TARGET
shuffled_r2 = []

for i in range(100):
    np.random.shuffle(Y)

    reg = LinearRegression()
    reg.fit(X,Y)

    ypred = reg.predict(X)
    shuffled_r2.append(r2_score(Y,ypred))

print(shuffled_r2[:20])
```