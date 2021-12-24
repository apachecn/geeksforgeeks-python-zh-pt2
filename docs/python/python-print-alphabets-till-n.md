# Python |打印字母表 till N

> 原文:[https://www . geesforgeks . org/python-print-alphabets-till-n/](https://www.geeksforgeeks.org/python-print-alphabets-till-n/)

有时，在使用 Python 时，我们可能会遇到一个问题，需要按顺序打印特定数量的字母。这可以在学校级编程中得到应用。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用回环+ `chr()`**
这是蛮力的方式来执行这个任务。在这种情况下，我们迭代元素，直到在使用 chr()转换为字符后需要相应地打印和连接字符串。

```
# Python3 code to demonstrate working of
# Print Alphabets till N
# Using loop

# initialize N 
N = 20

# printing N 
print("Number of elements required : " + str(N))

# Print Alphabets till N
# Using loop
res = ""
for idx in range(97, 97 + N):
       res = res + chr(idx) 

# printing result
print("Alphabets till N are : " + str(res))
```

**Output :**

```
Number of elements required : 20
Alphabets till N are : abcdefghijklmnopqrst

```