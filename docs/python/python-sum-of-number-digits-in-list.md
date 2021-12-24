# Python |列表中数字的总和

> 原文:[https://www . geesforgeks . org/python-列表中数字总和/](https://www.geeksforgeeks.org/python-sum-of-number-digits-in-list/)

求数字总和的问题很常见。这有时会以列表的形式出现，我们需要执行它。这在许多领域都有应用，如学校编程和网络开发。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用 loop + str()**
这是执行这个特定任务的蛮力方法。在本例中，我们对每个元素运行一个循环，将每个数字转换为字符串，并计算每个数字的总和。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Sum of number digits in List
# using loop + str()

# Initializing list
test_list = [12, 67, 98, 34]

# printing original list
print("The original list is : " + str(test_list))

# Sum of number digits in List
# using loop + str()
res = []
for ele in test_list:
    sum = 0
    for digit in str(ele):
        sum += int(digit)
    res.append(sum)

# printing result
print ("List Integer Summation : " + str(res))
```

**Output : **

```
The original list is : [12, 67, 98, 34]
List Integer Summation : [3, 13, 17, 7]
```