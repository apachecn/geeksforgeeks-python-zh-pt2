# Python–元组矩阵中的逐行元素添加

> 原文:[https://www . geesforgeks . org/python-row-wise-element-in-tuple-matrix/](https://www.geeksforgeeks.org/python-row-wise-element-addition-in-tuple-matrix/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即我们需要在元组矩阵中执行行方式的自定义元素添加。这种问题可以在数据领域得到应用。让我们讨论执行这项任务的某些方法。

> **输入** :
> 测试 _ 列表=[(' Gfg '，3)]，[('best '，1)]
> cus _ eles =[1，2]
> **输出**:[(' Gfg '，3，1)]，[('best '，1，2)]
> 
> **输入**:
> test _ list =[[[(' gfg '，6)、[' gfg '，3)]]
> cus _ them =【7]
> t5】输出:[[[[' gfg '，6.7]，[' gfg '，3.7)]]

**方法一:使用`enumerate()` +嵌套列表理解**
以上方法的组合可以解决这个问题。在本文中，我们通过枚举()使用嵌套列表理解和索引迭代来执行添加元素的任务。

```py
# Python3 code to demonstrate working of 
# Row-wise element Addition in Tuple Matrix
# Using enumerate() + list comprehension

# initializing list
test_list = [[('Gfg', 3), ('is', 3)], [('best', 1)], [('for', 5), ('geeks', 1)]]

# printing original list
print("The original list is : " + str(test_list))

# initializing Custom eles
cus_eles = [6, 7, 8]

# Row-wise element Addition in Tuple Matrix
# Using enumerate() + list comprehension
res = [[sub + (cus_eles[idx], ) for sub in val] for idx, val in enumerate(test_list)]

# printing result 
print("The matrix after row elements addition : " + str(res)) 
```

**Output :**

> 原列表为:【(' Gfg '，3)、(' is '，3)】、【(' best '，1)】、【(' for '，5)、(' geeks '，1)】】
> 行元素添加后的矩阵:【(' Gfg '，3，6)、(' is '，3，6)】、【(' best '，1，7)】、【(' for '，5，8)、(' geeks '，1，8)】

**方法二:使用`zip()` +列表理解**
以上功能的组合可以解决这个问题。在本例中，我们使用 zip()而不是 enumerate()来执行将新的行元素与相应的行进行组合的任务。

```py
# Python3 code to demonstrate working of 
# Row-wise element Addition in Tuple Matrix
# Using zip() + list comprehension

# initializing list
test_list = [[('Gfg', 3), ('is', 3)], [('best', 1)], [('for', 5), ('geeks', 1)]]

# printing original list
print("The original list is : " + str(test_list))

# initializing Custom eles
cus_eles = [6, 7, 8]

# Row-wise element Addition in Tuple Matrix
# Using zip() + list comprehension
res = [[(idx, val) for idx in key] for key,  val in zip(test_list, cus_eles)]

# printing result 
print("The matrix after row elements addition : " + str(res)) 
```

**Output :**

> 原列表为:【(' Gfg '，3)、(' is '，3)】、【(' best '，1)】、【(' for '，5)、(' geeks '，1)】】
> 行元素添加后的矩阵:【(' Gfg '，3，6)、(' is '，3，6)】、【(' best '，1，7)】、【(' for '，5，8)、(' geeks '，1，8)】