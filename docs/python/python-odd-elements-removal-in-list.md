# Python–列表中奇数元素的移除

> 原文:[https://www . geesforgeks . org/python-奇数-元素-列表中移除/](https://www.geeksforgeeks.org/python-odd-elements-removal-in-list/)

由于机器学习的即将到来，现在的焦点比以往任何时候都更加集中在处理某些值上，这背后的原因是，在数据被输入到进一步的技术中执行之前，这是数据预处理的关键步骤。因此，去除某些基本的价值观和对它的了解是必须的。让我们讨论消除奇数的某些方法。

**方法#1:天真方法**
在天真方法中，我们遍历整个列表，并将所有过滤后的非奇数值追加到一个新列表中，从而为后续操作做好准备。

```
# Python3 code to demonstrate 
# Odd elements removal in List
# using naive method 

# initializing list
test_list = [1, 9, 4, 7, 6, 5, 8, 3]

# printing original list 
print ("The original list is : " + str(test_list))

# using naive method 
# Odd elements removal in List
res = []
for val in test_list:
    if not (val % 2 != 0) :
        res.append(val)

# printing result
print ("List after removal of Odd values : " + str(res))
```

**Output :**

```
The original list is : [1, 9, 4, 7, 6, 5, 8, 3]
List after removal of Odd values : [4, 6, 8]

```