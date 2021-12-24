# Python–选择性连续后缀连接

> 原文:[https://www . geesforgeks . org/python-选择性-连续-后缀-join/](https://www.geeksforgeeks.org/python-selective-consecutive-suffix-join/)

给定一个元素列表，的任务是编写一个 Python 程序来根据每个字符串的后缀执行连续字符串的连接。

> **输入**:test _ list =[“Geeks-”、“for-”、“Geeks”、“is”、“best-”、“for”、“Geeks”，suff = '-'
> **输出**:[“Geeks-for-Geeks”、“is”、“best-for”、“Geeks”]
> **解释**:字符串接在以“-”为后缀的旁边。
> 
> **输入**:test _ list =[“Geeks *”、“for*”、“Geeks”、“is”、“best*”、“for”、“Geeks”，suf = ' *
> **输出**:[‘Geeks * for * Geeks’，‘is’，‘best * for’，‘Geeks’]
> **解释**:字符串接在以“*”为后缀的旁边。

**方法:使用** [**循环**](https://www.geeksforgeeks.org/python-for-loops/)**+**[**end swith()**](https://www.geeksforgeeks.org/string-endswith-python/)**+**[**join()**](https://www.geeksforgeeks.org/join-function-python/)

在本例中，我们使用 *join()* 执行连接任务，而 *endswith()* 执行定义的后缀条件检查任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Selective consecutive Suffix Join
# Using loop + endswith() + join()

# initializing list
test_list = ["Geeks-", "for-", "Geeks", "is",
             "best-", "for", "geeks"]

# printing original list
print("The original list is : " + str(test_list))

# initializing suffix
suff = '-'

res = []
temp = []
for ele in test_list:
    temp.append(ele)

    # conditionally test values
    if not ele.endswith(suff):
        res.append(''.join(temp))
        temp = []
if temp:
    res.append(''.join(temp))

# printing result
print("The joined result : " + str(res))
```

**输出:**

> 最初的名单是:['极客-'，'为-'，'极客'，'是'，'最佳-'，'为'，'极客']
> 加入的结果:['极客为极客'，'是'，'最佳为'，'极客'