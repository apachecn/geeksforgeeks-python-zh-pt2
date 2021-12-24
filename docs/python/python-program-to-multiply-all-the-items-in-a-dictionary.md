# Python 程序将字典中的所有项目相乘

> 原文:[https://www . geesforgeks . org/python-program-to-multiple-all-in-items-in-a-dictionary/](https://www.geeksforgeeks.org/python-program-to-multiply-all-the-items-in-a-dictionary/)

Python 程序举例说明将[字典](https://www.geeksforgeeks.org/python-dictionary/)中的所有项目相乘可以通过创建一个字典来完成，该字典将存储所有键值对，将所有键值相乘并将其存储在变量中。

**示例:**

> **输入:** dict = {'value1':5，' value2':4，' value3':3，' value4':2，' value 5 ':1 }
> T3】输出: ans = 120
> 
> **输入:**指令**=**{‘v1’:10，' v2':7，' v3 ':****输出:**年= 140**

**进场:**

*   创建一个字典 d，并在其中存储键值对。
*   创建一个初始化为 1 的变量答案。
*   运行循环遍历字典
*   将每个键值与答案相乘，并将结果存储在答案本身中。
*   打印答案。

以下是上述方法的示例。

**例 1:**

## 蟒蛇 3

```py
# create a dictionary
d = {
    'value1': 5,
    'value2': 4,
    'value3': 3,
    'value4': 2,
    'value5': 1,
}

# create a variable to store result
answer = 1

# run a loop
for i in d:
    answer = answer*d[i]

# print answer
print(answer)
```

**Output**

```py
120

```

**例 2:**

## 蟒蛇 3

```py
# create a dictionary
d = {
    'a': 10,
    'b': 7,
    'c': 2,
}

# create a variable to store result
answer = 1

# run a loop
for i in d:
    answer = answer*d[i]

# print answer
print(answer)
```

**Output**

```py
140

```