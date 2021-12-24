# 构建等位数元组的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序到构造-等位数-元组/](https://www.geeksforgeeks.org/python-program-to-construct-equidigit-tuples/)

给定元素列表，将元组列表分成相似的数字元组对。

> **输入** : test_list = [5654，223，982143，34，1021]
> **输出** : [(56，54)，(2，23)，(982，143)，(3，4)，(10，21)]
> **解释**:元组中元素等分布。
> 
> **输入**:test _ list =【5654，223，1021】
> **输出** : [(56，54)，(2，23)，(10，21)]
> **解释**:元组中元素分布均匀。

**方法#1:使用循环+切片+ str()**

在本例中，我们通过获取 mid-idx 来执行除法任务，然后从 mid 切片，最初使用 str()将整数分割为字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Construct Equidigit tuples
# Using loop + slicing str()

# initializing list
test_list = [5654, 223, 982143, 34, 1021]

# printing original list
print("The original list is : " + str(test_list))

res = []
for sub in test_list:

    # getting mid element
    mid_idx = len(str(sub)) // 2

    # slicing Equidigits
    el1 = str(sub)[:mid_idx]
    el2 = str(sub)[mid_idx:]

    res.append((int(el1), int(el2)))

# printing result 
print("Equidigit tuples List : " + str(res))
```

**输出:**

> 原列表为:【5654，223，982143，34，1021】
> 等位数元组列表:[(56，54)，(2，23)，(982，143)，(3，4)，(10，21)]