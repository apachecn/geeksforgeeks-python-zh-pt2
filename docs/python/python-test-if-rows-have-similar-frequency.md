# Python–测试行是否具有相似的频率

> 原文:[https://www . geeksforgeeks . org/python-test-if-row-具有相似的频率/](https://www.geeksforgeeks.org/python-test-if-rows-have-similar-frequency/)

在本文中，我们有一个给定的矩阵，测试是否所有的行都有相似的元素。

> **输入** : test_list = [[6，4，2，7，3]，[7，3，6，4，2]，[2，4，7，3，6]]
> **输出** : True
> **解释**:所有列表都有 2，3，4，6，7。
> **输入** : test_list = [[6，4，2，7，3]，[7，5，6，4，2]，[2，4，7，3，6]]
> **输出** : False
> **说明**:第 2 个 list 有 5 个而不是 3 个。

**方法一:使用 Counter() +列表理解**

在本文中，我们使用 Counter()计算元素的频率字典，并与 Matrix 中的每一行进行比较，如果它们被检出，则返回 True。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Test if Rows have Similar frequency
# Using Counter() + list comprehension
from collections import Counter

# initializing list
test_list = [[6, 4, 2, 7, 3], [7, 3, 6, 4, 2], [2, 4, 7, 3, 6]]

# printing original list
print("The original list is : " + str(test_list))

# checking if all rows are similar 
res = all(dict(Counter(row)) == dict(Counter(test_list[0])) for row in test_list)

# printing result 
print("Are all rows similar : " + str(res))
```

**Output**

> 原始列表为:[[6，4，2，7，3]，[7，3，6，4，2]，[2，4，7，3，6]]
> 所有行都相似吗:真

**方法 2:使用列表理解+排序()+ all()**

在本文中，我们使用 sorted()通过将所有元素排序为排序格式来检查相似的元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Test if Rows have Similar frequency
# Using list comprehension + sorted() + all()

# initializing list
test_list = [[6, 4, 2, 7, 3], [7, 3, 6, 4, 2], [2, 4, 7, 3, 6]]

# printing original list
print("The original list is : " + str(test_list))

# checking if all rows are similar 
# ordering each row to test 
res = all(list(sorted(row)) == list(sorted(test_list[0])) for row in test_list)

# printing result 
print("Are all rows similar : " + str(res))
```

**Output**

> 原始列表为:[[6，4，2，7，3]，[7，3，6，4，2]，[2，4，7，3，6]]
> 所有行都相似吗:真