# 机器学习问题 Pywedge 包

> 原文:[https://www . geeksforgeeks . org/py wedge-package-for-machine-learning-problems/](https://www.geeksforgeeks.org/pywedge-package-for-machine-learning-problems/)

当人们开始学习机器学习和数据科学时，他们总是会听到的一个事实/观察是，将机器学习模型拟合到数据集很容易，但为任务准备数据集却不容易。在解决 ML 问题时，我们经常需要经历一系列的步骤，然后才能真正找到最适合数据集的 ML 算法。很少有主要步骤可以命名为:

1.  **Data collection:** It can be collected from various sources, either from real life data or manually.
2.  **Data set preprocessing:** After collecting raw data, we need to convert it into meaningful form so that the algorithm can explain it well. It also includes a series of steps, such as-using exploratory data analysis to understand data and deleting missing values in data set (by interpolation method/manually).
3.  **Feature engineering:** In feature engineering, we use different methods such as [Chi-square test](https://www.geeksforgeeks.org/ml-chi-square-test-for-feature-selection/?ref=rp) and use [additional tree classifier](https://www.geeksforgeeks.org/ml-extra-tree-classifier-for-feature-selection/) to realize the process of converting classified features into numerical features, standardization, normalization and feature selection.
4.  **Handling of data set imbalance:** Sometimes the data set we collected is in a highly unbalanced state. Fitting any model to this type of data set will bring us inaccurate results, because the model always tends to the frequently occurring data in the data set.
5.  **Making a baseline model:** In this case, we fit different maximum likelihood algorithms to our data and try to find out which model gives us more accurate results.
6.  **superparameter adjustment:** After we select the best model from all models, we adjust the superparameter of the model to improve the accuracy of the model by solving the problem of under-fitting/over-fitting.

因此，我们可以得出结论，在得到我们想要的结果之前，我们必须经历许多不同的步骤。就时间而言，大约 80%的时间消耗在数据准备上，这样模型就可以适应它，剩下的 20%需要用于适应最大似然算法和进行预测。因此，执行所有这些任务肯定是一项详尽的任务，但是如果我们可以使用一些方法/函数/库，使我们的这项任务变得容易，那该怎么办。

在本文中，我们将阅读一个名为 **Pywedge** 的开源 python 包。

### 什么是 Pywedge？

Pywedge 是一个开源的 python 包，可 pip 安装，由 **Venkatesh Rengarajan Muthu** 开发，它可以帮助我们以一种非常交互的方式，自动完成为数据预处理、数据可视化、特征工程、处理不平衡数据以及制作标准基线模型、超参数调优等编写代码的任务。

**py wedge 的特点:**

1.  It can make 8 different types of interactive charts, such as scatter chart, pie chart, box chart, bar chart and histogram.
2.  Use interactive methods to preprocess data, such as dealing with missing values, converting classification features into digital features, standardization, normalization, dealing with class imbalance and so on.
3.  It will automatically fit our data into different ML algorithms and give 10 best baseline models.
4.  We can also apply superparameter adjustment to the model we want.

让我们使用这个 pywedge 库来解决一个回归问题，其中我们必须使用取自[**Dockship 的电厂能量预测 AI 挑战赛**](https://dockship.io/challenges/5fa1f40ac2a4984b34ef0a66/power-plant-energy-prediction-ai-challenge/overview) **的数据集来预测电厂产生的能量。**

#### 导入重要的库

## 蟒蛇 3

```
import numpy as np
import pandas as pd
import warnings
warnings.filterwarnings("ignore")
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error
```

**加载训练和测试数据集:**

## Python

```
# Loading testing Data
test_data = pd.read_csv("TEST.csv")
# Loading training Data
data = pd.read_csv("TRAIN.csv")
# Printing the shape of train dataset
data.shape
```

```
(8000, 5)
```

现在，我们将使用 head()方法检查数据集的外观，并在后续步骤中检查它的一些信息，如下所示:

## 【Python】

```
data.head()
```