# Python–测试独特频率

> 原文:[https://www . geesforgeks . org/python-测试独特频率/](https://www.geeksforgeeks.org/python-test-for-unique-frequencies/)

给定一个列表，找出每个值元素的频率本身是否是唯一值。

> **输入**:test _ list =【4、3、2】
> **输出** : False
> **解释**:均有 1 为频率，故为双工，故为 False
> **输入**:test _ list =【4、3、3、2、2、2】
> **输出** : True
> **解释** : 1、2、3 分别为 4、3、2 的频率，唯一

**方法#1:使用 loop + set()**
上述功能的组合提供了解决这个问题的强力方式。在这种情况下，我们通过增加出现值的索引来记住元素的频率。然后 set()用于删除重复项，并测试其长度是否与转换前相同。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test for Unique Frequencies
# Using loop + set()

# initializing list
test_list = [4, 3, 2, 2, 3, 4, 4, 4, 1, 2]

# printing original list
print("The original list : " + str(test_list))

# Test for Unique Frequencies
res = False
temp = [0] * 5
for ele in test_list:

    # performing memoization in temp list
    temp[ele] += 1
mem_list = temp[1:]

# checking for set converted list length with original list
if len(list(set(mem_list))) == len(mem_list):
    res = True

# printing result
print("Are element's Frequencies Unique ? : " + str(res))
```

**Output : **

```
The original list : [4, 3, 2, 2, 3, 4, 4, 4, 1, 2]
Are element's Frequencies Unique ? : True
```

**方法#2:使用 setdefault() + values()**
上述函数的组合提供了解决这个问题的另一种方法。在这种情况下，字典用于记忆，元素频率被记录为值。最后，比较相似的取值步骤和字典键数是否相等。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test for Unique Frequencies
# Using setdefault() + values()

# initializing list
test_list = [4, 3, 2, 2, 3, 4, 4, 4, 1, 2]

# printing original list
print("The original list : " + str(test_list))

# Test for Unique Frequencies
# Using setdefault() + values()
temp = {}
for ele in test_list:

    # setting default value to 0
    temp.setdefault(ele, 0)
    temp[ele] += 1

# checking for values and keys equality
res = len(set(temp.values())) == len(temp)

# printing result
print("Are element's Frequencies Unique ? : " + str(res))
```

**Output : **

```
The original list : [4, 3, 2, 2, 3, 4, 4, 4, 1, 2]
Are element's Frequencies Unique ? : True
```