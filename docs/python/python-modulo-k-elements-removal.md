# Python–模 K 元素移除

> 原文:[https://www . geeksforgeeks . org/python-模-k-elements-remove/](https://www.geeksforgeeks.org/python-modulo-k-elements-removal/)

由于机器学习的即将到来，现在的焦点比以往任何时候都更加集中在处理某些值上，这背后的原因是，在数据被输入到进一步的技术中执行之前，这是数据预处理的关键步骤。因此，去除某些基本的价值观和对它的了解是必须的。让我们讨论实现去除模 K 值的某些方法。

**方法#1:天真方法**
在天真方法中，我们遍历整个列表，并将所有过滤后的非模 K 值追加到一个新列表中，从而准备好执行后续操作。

```py
# Python3 code to demonstrate 
# Modulo K elements removal
# using naive method 

# initializing list
test_list = [1, 9, 4, 7, 6, 5, 8, 3]

# printing original list 
print ("The original list is : " + str(test_list))

# initializing K 
K = 3

# using naive method 
# Modulo K elements removal
res = []
for val in test_list:
    if (val % K) :
        res.append(val)

# printing result
print ("List after removal of modulo K values : " + str(res))
```

**Output :**

```py
The original list is : [1, 9, 4, 7, 6, 5, 8, 3]
List after removal of modulo K values : [1, 4, 7, 5, 8]

```