# Python–递增字典测试

> 原文:[https://www . geesforgeks . org/python-test-for-increment-dictionary/](https://www.geeksforgeeks.org/python-test-for-incrementing-dictionary/)

给定一个字典，测试它是否增加，即它的键和值增加 1。

> **输入** : test_dict = {1:2，3:4，5:6，7:8}
> **输出** : True
> **解释**:所有键和值按顺序相差 1。
> 
> **输入** : test_dict = {1:2，3:10，5:6，7:8}
> **输出** : False
> **解释**:不规则项。

**方法:使用项目()+循环+扩展()+列表理解**

在这种情况下，第一步是使用*项()* +列表理解和*扩展()*获得字典到列表的转换，下一个循环用于测试转换后的列表是否是增量的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Test for Incrementing Dictionary
# Using extend() + list comprehension

# initializing dictionary
test_dict = {1: 2, 3: 4, 5: 6, 7: 8}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

temp = []

# forming list from dictionary
[temp.extend([key, val]) for key, val in test_dict.items()]

# checking for incrementing elements
res = True
for idx in range(0, len(temp) - 1):

    # test for increasing list
    if temp[idx + 1] - 1 != temp[idx]:
        res = False

# printing result
print("Is dictionary incrementing : " + str(res))
```

**输出:**

```py
The original dictionary is : {1: 2, 3: 4, 5: 6, 7: 8}
Is dictionary incrementing : True
```