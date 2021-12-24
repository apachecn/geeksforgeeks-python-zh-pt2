# Python 程序，检查字典的值是否与列表中的值顺序相同

> 原文:[https://www . geesforgeks . org/python-program-to-check-a-values-a-dictionary-in-list-in-order-as-in-list/](https://www.geeksforgeeks.org/python-program-to-check-whether-the-values-of-a-dictionary-are-in-same-order-as-in-a-list/)

给定一个字典，测试值是否与列表值一致。

> **输入**:test _ dict = {“gfg”:4、“is”:10、“best”:11 }、sub_list = [4、10、11]
> **输出** : True
> **解释**:值为 4、10、11，与列表顺序相同。因此返回真。
> 
> **输入**:test _ dict = {“gfg”:4、“is”:10、“best”:11 }、sub_list = [4、11、10]
> **输出** : False
> **解释**:值为 4、10、11，列表顺序为 4、11、10，不是同一个顺序。因此返回假。

**方法#1:使用** [**循环**](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，我们迭代字典值并列出，测试是否所有的值都是有序的，如果有任何元素是无序的，则标记为 off。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Test for Ordered values from List
# Using loop

# initializing dictionary
test_dict = {"gfg" : 4, "is" : 10, "best" : 11, "for" : 19, "geeks" : 1}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing list 
sub_list = [4, 10, 11, 19, 1]

idx = 0
res = True
for key in test_dict:

    # checking for inequality in order
    if test_dict[key] != sub_list[idx]:
        res = False
        break
    idx += 1

# printing result 
print("Are values in order : " + str(res)) 
```

**输出:**

> 最初的字典是:{'gfg': 4，' is': 10，' best': 11，' for': 19，' geeks': 1}
> 是按顺序排列的值:True

**方法 2:使用** [**值()**](https://www.geeksforgeeks.org/python-dictionary-values/) **+** [**比较**](https://www.geeksforgeeks.org/python-operators/) **运算符**

在本例中，我们使用 values()提取所有值，然后使用比较运算符检查与 list 的相等性。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Test for Ordered values from List
# Using values() + comparison operators

# initializing dictionary
test_dict = {"gfg" : 4, "is" : 10, "best" : 11, "for" : 19, "geeks" : 1}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing list 
sub_list = [4, 10, 11, 19, 1]

# comparing values with list
res = list(test_dict.values()) == sub_list

# printing result 
print("Are values in order : " + str(res)) 
```

**输出:**

> 最初的字典是:{'gfg': 4，' is': 10，' best': 11，' for': 19，' geeks': 1}
> 是按顺序排列的值:True