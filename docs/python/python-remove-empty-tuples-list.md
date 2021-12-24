# Python |从列表中移除空元组

> 原文:[https://www . geesforgeks . org/python-remove-empty-元组-list/](https://www.geeksforgeeks.org/python-remove-empty-tuples-list/)

在本文中，我们将看到如何从给定的元组列表中移除空元组。我们将找到各种方法，在这些方法中，我们可以使用 Python 中的各种方法来执行移除元组的任务。
示例:

```
Input : tuples = [(), ('ram','15','8'), (), ('laxman', 'sita'), 
                  ('krishna', 'akbar', '45'), ('',''),()]
Output : [('ram', '15', '8'), ('laxman', 'sita'), 
          ('krishna', 'akbar', '45'), ('', '')]

Input : tuples = [('','','8'), (), ('0', '00', '000'), 
                 ('birbal', '', '45'), (''), (),  ('',''),()]
Output : [('', '', '8'), ('0', '00', '000'), ('birbal', '', 
          '45'), ('', '')]

```

**方法一:利用[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)T3 的概念**

```
# Python program to remove empty tuples from a 
# list of tuples function to remove empty tuples 
# using list comprehension
def Remove(tuples):
    tuples = [t for t in tuples if t]
    return tuples

# Driver Code
tuples = [(), ('ram','15','8'), (), ('laxman', 'sita'), 
          ('krishna', 'akbar', '45'), ('',''),()]
print(Remove(tuples))
```

输出:

```
[('ram', '15', '8'), ('laxman', 'sita'), ('krishna', 
                           'akbar', '45'), ('', '')]

```

**方法二:使用 filter()方法**
使用 Python 中内置的方法 filter()，我们可以通过传递 *None* 作为参数来过滤掉空元素。这种方法在 Python 2 和 Python 3 及更高版本中都有效，但是所需的输出只在 Python 2 中显示，因为 Python 3 返回一个生成器。filter()是比列表理解更快的方法。让我们看看当我们在 Python 2 中运行程序时会发生什么。

```
# Python2 program to remove empty tuples
# from a list of tuples function to remove 
# empty tuples using filter
def Remove(tuples):
    tuples = filter(None, tuples)
    return tuples

# Driver Code
tuples = [(), ('ram','15','8'), (), ('laxman', 'sita'), 
          ('krishna', 'akbar', '45'), ('',''),()]
print Remove(tuples)
```

输出:

```
[('ram', '15', '8'), ('laxman', 'sita'), ('krishna', 'akbar', '45'), ('', '')]
```

现在让我们看看当我们尝试在 Python 3 及更高版本中运行程序时会发生什么。在 Python 3 中运行程序时，如前所述，会返回一个生成器。

```
# Python program to remove empty tuples from 
# a list of tuples function to remove empty 
# tuples using filter
def Remove(tuples):
    tuples = filter(None, tuples)
    return tuples

# Driver Code
tuples = [(), ('ram','15','8'), (), ('laxman', 'sita'), 
          ('krishna', 'akbar', '45'), ('',''),()]
print (Remove(tuples))
```

输出:

```
<filter object at 0x7fe26eb0f3c8>
```