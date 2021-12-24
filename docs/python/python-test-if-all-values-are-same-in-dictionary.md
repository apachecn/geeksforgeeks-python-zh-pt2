# Python–测试字典中所有值是否相同

> 原文:[https://www . geesforgeks . org/python-test-如果所有值在字典中都相同/](https://www.geeksforgeeks.org/python-test-if-all-values-are-same-in-dictionary/)

给定一个字典，测试它的所有值是否相同。

> **输入**:test _ dict = {“Gfg”:8、“is”:8、“Best”:8 }
> **输出** : True
> **解释**:所有元素值相同，8。
> 
> **输入**:test _ dict = {“Gfg”:8、“is”:8、“Best”:9 }
> **输出** : False
> **解释**:所有元素值不一样。

**方法#1:使用循环**

这是执行这项任务的方法之一。在这种情况下，我们对所有值进行迭代，并与字典中的值进行比较，如果任何一个值不同，则返回 False。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Test if all Values are Same in Dictionary 
# Using loop

# initializing dictionary
test_dict = {"Gfg" : 5, "is" : 5, "Best" : 5}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Flag to check if all elements are same 
res = True 

# extracting value to compare
test_val = list(test_dict.values())[0]

for ele in test_dict:
    if test_dict[ele] != test_val:
        res = False 
        break

# printing result 
print("Are all values similar in dictionary? : " + str(res)) 
```

**Output**

```
The original dictionary is : {'Gfg': 5, 'is': 5, 'Best': 5}
Are all values similar in dictionary? : True

```

**方法 2:使用 set() + values() + len()**

这是执行这项任务的另一种方式。在本例中，我们使用 values()提取所有值，set()用于删除重复项。如果提取集的长度是 1，那么所有的值都被认为是相似的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Test if all Values are Same in Dictionary 
# Using set() + values() + len()

# initializing dictionary
test_dict = {"Gfg" : 5, "is" : 5, "Best" : 5}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# using set() to remove duplicates and check for values count
res = len(list(set(list(test_dict.values())))) == 1

# printing result 
print("Are all values similar in dictionary? : " + str(res)) 
```

**Output**

```
The original dictionary is : {'Gfg': 5, 'is': 5, 'Best': 5}
Are all values similar in dictionary? : True

```