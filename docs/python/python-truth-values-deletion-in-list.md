# Python–列表中的真值删除

> 原文:[https://www . geesforgeks . org/python-真值表-列表中删除/](https://www.geeksforgeeks.org/python-truth-values-deletion-in-list/)

由于机器学习的即将到来，焦点现在比以往任何时候都更加集中在处理值上，这背后的原因是，在数据被输入到进一步的技术中执行之前，它是数据预处理的关键步骤。因此，从本质上去除价值，无论它是无，还是有时是真理，对它的了解是必须的。让我们讨论实现这一目标的某些方法。

**方法#1:天真方法**
在天真方法中，我们遍历整个列表，并将所有过滤后的无值追加到一个新列表中，从而准备好执行后续操作。

```py
# Python3 code to demonstrate 
# Truth values deletion in List
# using naive method 

# initializing list
test_list = [1, None, 4, None, False, 5, 8, False]

# printing original list 
print ("The original list is : " + str(test_list))

# using naive method 
# Truth values deletion in List
res = []
for val in test_list:
    if not val:
        res.append(val)

# printing result
print ("List after removal of Truth values : " + str(res))
```

**Output :**

```py
The original list is : [1, None, 4, None, False, 5, 8, False]
List after removal of Truth values : [None, None, False, False]

```