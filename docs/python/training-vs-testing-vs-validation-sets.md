# 培训、测试和验证集

> 原文:[https://www . geesforgeks . org/training-vs-testing-vs-validation-set/](https://www.geeksforgeeks.org/training-vs-testing-vs-validation-sets/)

在本文中，我们将看到如何训练、测试和验证集合。

分割数据集的基本目的是评估训练好的模型在推广到新数据方面的有效性。使用 [scikit-learn 的 **train_test_split** 功能可以实现此拆分。](https://www.geeksforgeeks.org/learning-model-building-scikit-learn-python-machine-learning-library/)

## **训练集**

这是模型训练的实际数据集，即模型从这些数据中看到并学习，以预测结果或做出正确的决策。大多数训练数据是从几个资源中收集的，然后进行预处理和组织，以提供模型的适当性能。训练数据的类型极大地决定了模型的泛化能力，即训练数据的质量和多样性越好，模型的性能就越好。该数据占项目可用总数据的 60%以上。

**示例:**

## 蟒蛇 3

```py
# Importing numpy & scikit-learn
import numpy as np
from sklearn.model_selection import train_test_split

# Making a dummy array to
# represent x,y for example
# Making a array for x ranging
# from 0-15 then reshaping it
# to form a matrix of shape 8x2
x = np.arange(16).reshape((8,2))

# y is just a list of 0-7 number
# representing target variable
y = range(8)

# Splitting dataset in 80-20 fashion .i.e. 
# Testing set is 20% of total data
# Training set is 80% of total data
x_train, x_test, y_train, y_test = train_test_split(x,y,
                                                    train_size=0.8, 
                                                    random_state=42)

# Training set 
print("Training set x: ",x_train)
print("Training set y: ",y_train)
```

**输出:**

```py
Training set x:  [[ 0  1]
 [14 15]
 [ 4  5]
 [ 8  9]
 [ 6  7]
 [12 13]]
Training set y:  [0, 7, 2, 4, 3, 6]
```

**说明:**

*   首先，我们使用 NumPy 库创建了一个 8×2 形状的虚拟矩阵来表示输入 x，并创建了一个 0 到 7 个整数的列表来表示我们的目标变量 y
*   现在为了将我们的数据集分割成训练和测试数据，使用了 sklearn 库名为 **train_test_split** 的函数。
*   将带有目标变量 y 的输入数据 x 作为参数传递给函数，然后函数根据 train_size 中给定的大小将数据集分成两部分，即如果 train_size=0.8，则数据集将以这样的方式进行划分，即训练集占给定数据集的 80%，测试集占给定数据集的 20%。
*   当我们指定 random_state 为正数时，train_test_split 函数将随机分割数据。

## **测试装置**

该数据集独立于训练集，但具有某种相似类型的类概率分布，并用作评估模型的基准，仅在模型训练完成后使用。测试集通常是一个适当组织的数据集，包含模型在现实世界中使用时可能面临的场景的各种数据。通常，验证和测试集结合起来用作测试集，这并不被认为是一个好的实践。如果模型在训练数据上的准确性大于在测试数据上的准确性，那么该模型被称为具有过拟合。该数据约占项目可用总数据的 20-25%。

**示例:**

## 蟒蛇 3

```py
# Importing numpy & scikit-learn
import numpy as np
from sklearn.model_selection import train_test_split

# Making a dummy array to represent x,y for example
# Making a array for x ranging from 0-15 then
# reshaping it to form a matrix of shape 8x2
x = np.arange(16).reshape((8, 2))

# y is just a list of 0-7 number representing 
# target variable
y = range(8)

# Splitting dataset in 80-20 fashion .i.e.
# Training set is 80% of total data
# Testing set is 20% of total data
x_train, x_test, y_train, y_test = train_test_split(x, y,
                                                    test_size=0.2,
                                                    random_state=42)

# Testing set
print("Testing set x: ", x_test)
print("Testing set y: ", y_test)
```

**输出:**

```py
Testing set x:  [[ 2  3]
 [10 11]]
Testing set y:  [1, 5]
```

**说明:**

*   为了展示 train_test_split 函数是如何工作的，我们首先使用 NumPy 库创建了一个 8×2 形状的虚拟矩阵来表示输入 x，以及一个表示目标变量 y 的 0 到 7 个整数的列表
*   现在，为了将我们的数据集划分为训练数据和测试数据，将带有目标变量 y 的输入数据 x 作为参数传递给函数，然后函数根据 test_size 中给出的大小将数据集划分为两部分，即如果 test_size=0.2，那么数据集将被划分为测试集占给定数据集的 20%，训练集占给定数据集的 80%。
*   当我们指定 random_state 为正数时，train_test_split 函数将随机分割数据。

## **验证集**

验证集用于微调模型的超参数，并被视为模型训练的一部分。模型只看到这些数据进行评估，而没有从这些数据中学习，从而提供了对模型的客观公正的评估。当验证数据集的损失大于训练数据集的损失时，也可以通过中断模型的训练来利用验证数据集进行回归，即减少偏差和方差。该数据约占项目可用总数据的 10-15%，但这可能会根据超参数的数量而变化，即如果模型有相当多的超参数，则使用大的验证集会给出更好的结果。现在，只要模型在验证数据上的准确性大于在训练数据上的准确性，那么就可以说该模型具有良好的通用性。

**示例:**

## 蟒蛇 3

```py
# Importing numpy & scikit-learn
import numpy as np
from sklearn.model_selection import train_test_split

# Making a dummy array to represent x,y for example
# Making a array for x ranging from 0-23 then reshaping it
# to form a matrix of shape 8x3
x = np.arange(24).reshape((8,3))

# y is just a list of 0-7 number representing 
# target variable
y = range(8)

# Splitting dataset in 80-20 fashion .i.e. 
# Training set is 80% of total data
# Combined set of testing & validation is 
# 20% of total data
x_train, x_Combine, y_train, y_Combine = train_test_split(x,y,
                                              train_size=0.8,
                                              random_state=42)

# Splitting combined dataset in 50-50 fashion .i.e. 
# Testing set is 50% of combined dataset
# Validation set is 50% of combined dataset
x_val, x_test, y_val, y_test = train_test_split(x_Combine,
                                                y_Combine,
                                                test_size=0.5,
                                                random_state=42)

# Training set 
print("Training set x: ",x_train)
print("Training set y: ",y_train)
print("  ")

# Testing set 
print("Testing set x: ",x_test)
print("Testing set y: ",y_test)
print("  ")

# Validation set 
print("Validation set x: ",x_val)
print("Validation set y: ",y_val)
```

**输出:**

```py
Training set x:  [[ 0  1  2]
 [21 22 23]
 [ 6  7  8]
 [12 13 14]
 [ 9 10 11]
 [18 19 20]]
Training set y:  [0, 7, 2, 4, 3, 6]

Testing set x:  [[15 16 17]]
Testing set y:  [5]

Validation set x:  [[3 4 5]]
Validation set y:  [1]
```

**说明:**

*   为了获得验证集，使用 NumPy 库创建了一个 8×3 形状的虚拟矩阵来表示输入 x，以及一个表示目标变量 y 的 0 到 7 个整数的列表
*   现在把数据集分成 3 部分有点棘手。首先，数据集被分成两部分，带有目标变量 y 的输入数据 x 作为参数传递给函数，然后函数根据 train_size 中给定的大小将数据集分成两部分(由此我们将得到我们的训练集)，即如果 train_size=0.8，那么数据集将以这样的方式被划分，训练集将是给定数据集的 80%，另一个集将是给定数据集的 20%。
*   因此，现在我们有了验证和测试组合集，其中包含最初给定数据集的 20%。该数据集被进一步划分以获得验证集和测试集，然后将上述分布的输出作为参数再次传递给 train_test_split，然后 train _ test _ split 根据 test_size 中给出的大小将组合数据集划分为 2 个部分，即如果 test_size=0.5，则数据集将以测试集和验证集为组合数据集的 50%的方式划分。