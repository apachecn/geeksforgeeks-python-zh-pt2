# Python–测试所需的字符串长度

> 原文:[https://www . geesforgeks . org/python-test-for-desired-string-length/](https://www.geeksforgeeks.org/python-test-for-desired-string-lengths/)

给定一个字符串列表，检查所有字符串是否与第二个大小列表中的所需字符串长度匹配。

> **输入**:test _ list =[“Gfg”、‘for’、‘极客’]、len_list = [3，3，5]
> **输出** : True
> **解释**:都是想要的长度。
> 
> **输入**:test _ list =[“Gfg”，“for”，“geek”]，len_list = [3，3，5]
> **输出** : False
> **解释** : geek 有 len 4，但期望是 5。

**方法#1:使用循环**

在这种情况下，我们对所有字符串进行迭代，如果我们得到任何与所需大小不匹配的字符串，则将结果标记为 false。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Test for desired String Lengths
# Using loop

# initializing string list
test_list = ["Gfg", 'is', 'best', 'for', 'geeks']

# printing original list
print("The original list is : " + str(test_list))

# initializing Lengths list 
len_list = [3, 2, 4, 3, 5]

res = True
for idx in range(len(test_list)):

    # checking for string lengths
    if len(test_list[idx]) != len_list[idx]:
        res = False
        break

# printing result 
print("Are all strings of required lengths : " + str(res))
```

**Output**

```
The original list is : ['Gfg', 'is', 'best', 'for', 'geeks']
Are all strings of required lengths : True

```

**方法 2:使用 all()**

如果所有长度都与其他列表中的所需长度相匹配，则返回“真”。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test for desired String Lengths
# Using all()

# initializing string list
test_list = ["Gfg", 'is', 'best', 'for', 'geeks']

# printing original list
print("The original list is : " + str(test_list))

# initializing Lengths list
len_list = [3, 2, 4, 3, 5]

# all() used to check for each element for length
res = all(len(test_list[idx]) == len_list[idx]
          for idx in range(len(test_list)))

# printing result
print("Are all strings of required lengths : " + str(res))
```

**Output**

```
The original list is : ['Gfg', 'is', 'best', 'for', 'geeks']
Are all strings of required lengths : True

```