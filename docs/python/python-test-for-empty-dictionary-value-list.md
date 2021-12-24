# Python–测试空字典值列表

> 原文:[https://www . geesforgeks . org/python-空字典测试-值列表/](https://www.geeksforgeeks.org/python-test-for-empty-dictionary-value-list/)

给定一个以列表作为值的字典，检查是否所有列表都是空的。

> **输入**:{“Gfg”:[]，“Best”:[]}
> **输出**:真
> **说明**:两个列表都没有元素，因此为真。
> 
> **输入**:{“Gfg”:[]，“Best”:[4]}
> **输出**:假
> **解释**:“Best”包含元素，故为假。

**方法#1:使用任意()+值()**

以上功能的组合可以用来解决这个任务。在这种情况下，我们检查使用 values()提取的值中是否存在任何值，如果没有找到，则列表为空。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Test for Empty Dictionary Value List
# Using any() + values()

# initializing dictionary
test_dict = {"Gfg" : [], "Best" : [], "is" : []}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# checking if any value is found 
# using not to negate the result of any()
res = not any(test_dict.values())

# printing result 
print("Are value lists empty? : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': [], 'Best': [], 'is': []}
Are value lists empty? : True

```

**方法 2:使用所有()+值()**

这是我们解决问题的另一种方法。在这种情况下，我们可以使用 all()检查每个键的所有值是否都为空。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Test for Empty Dictionary Value List
# Using all() + values()

# initializing dictionary
test_dict = {"Gfg" : [], "Best" : [], "is" : []}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# checking if all keys have empty list  
res = all(ele == [] for ele in list(test_dict.values()))

# printing result 
print("Are value lists empty? : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': [], 'Best': [], 'is': []}
Are value lists empty? : True

```