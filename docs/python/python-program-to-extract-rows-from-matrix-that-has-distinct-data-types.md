# 从矩阵中提取具有不同数据类型的行的 Python 程序

> 原文:[https://www . geeksforgeeks . org/python-从具有不同数据类型的矩阵中提取行的程序/](https://www.geeksforgeeks.org/python-program-to-extract-rows-from-matrix-that-has-distinct-data-types/)

给定一个矩阵，任务是编写一个 python 程序来提取没有重复数据类型的行。

**示例:**

> **输入:** test_list = [[4，3，1]，[“gfg”，3，{4:2}]，[3，1，“jkl”]，[9，(2，3)]
> 
> **输出:** [['gfg '，3，{4: 2}]，[9，(2，3)]
> 
> **说明:**【4，3，1】均为整数，故省略。[9，(2，3)]有整数和元组，不同的数据类型，因此包含在结果中。
> 
> **输入:** test_list = [[4，3，1]，[“gfg”，3，{4:2}，4]，[3，1，“jkl”]，[9，(2，3)]
> 
> **输出:** [[9，(2，3)]
> 
> **说明:**【4，3，1】均为整数，故省略。[9，(2，3)]有整数和元组，不同的数据类型，因此包含在结果中。

**法:使用** [**式()**](https://www.geeksforgeeks.org/python-type-function/) **+** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

在这种情况下，我们使用 type()检查行的每个元素的数据类型，如果数据类型重复，则结果中不包括该行。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Distinct Data Type Rows
# Using type() + list comprehension

# initializing list
test_list = [[4, 3, 1], ["gfg", 3, {4: 2}], [3, 1, "jkl"], [9, (2, 3)]]

# printing original list
print("The original list is : " + str(test_list))

res = []
for sub in test_list:

    # get Distinct types size
    type_size = len(list(set([type(ele) for ele in sub])))

    # if equal get result
    if len(sub) == type_size:
        res.append(sub)

# printing result
print("The Distinct data type rows : " + str(res))
```

**输出:**

> 原始列表为:[[4，3，1]，['gfg '，3，{4: 2}]，[3，1，' jkl']，[9，(2，3)]
> 
> 不同的数据类型行:[['gfg '，3，{4: 2}]，[9，(2，3)]