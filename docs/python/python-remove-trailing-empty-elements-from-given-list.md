# Python |从给定列表中移除尾随的空元素

> 原文:[https://www . geesforgeks . org/python-remove-trading-empty-elements-from-给定列表/](https://www.geeksforgeeks.org/python-remove-trailing-empty-elements-from-given-list/)

给定一个列表，任务是从列表的最后一个移除尾随的*无*值。让我们讨论几个解决给定任务的方法。

**示例:**

```py
Input: [1, 2, 3, 4, None, 76, None, None]
Output:  [1, 2, 3, 4, None, 76]

Input: [1, 2, None, None, None, None, None, 5]
Output:  [1, 2, None, None, None, None, None, 5]
```

**方法#1:使用幼稚的方法**

```py
# Python code to demonstrate
# to remove trailing None
# elements from lists

# initialising lists
ini_list = [1, 2, 3, 4, None, 76, None, None, None]

# printing initial dictionary
print ("initial dictionary", str(ini_list))

# code toremove trailing None values
# from lists
while not ini_list[-1]:
    ini_list.pop()

# printing result
print ("resultant list", str(ini_list))
```

**Output:**

```py
initial dictionary [1, 2, 3, 4, None, 76, None, None, None]
resultant list [1, 2, 3, 4, None, 76]

```

**方法 2:使用`itertools.dropwhile()`**

```py
# Python code to demonstrate
# to remove trailing None
# elements from lists

from itertools import dropwhile
# initialising lists
ini_list = [1, 2, 3, 4, None, 76, None, None, None]

# printing initial dictionary
print ("initial dictionary", str(ini_list))

# code toremove trailing None values
# from lists
res = list(reversed(tuple(dropwhile(lambda x: x is None, 
                                    reversed(ini_list)))))

# printing result
print ("resultant list", str(res))
```

**Output:**

```py
initial dictionary [1, 2, 3, 4, None, 76, None, None, None]
resultant list [1, 2, 3, 4, None, 76]

```

**方法 3:使用`itertools.takewhile()`**

```py
# Python code to demonstrate
# to remove trailing None
# elements from lists

from itertools import takewhile

# initialising lists
ini_list = [1, 2, 3, 4, None, 76, None, None, None]

# printing initial dictionary
print ("initial dictionary", str(ini_list))

# code toremove trailing None values
# from lists
res = ini_list[:-len(list(takewhile(lambda x: x == None,
                                  reversed(ini_list))))]
# printing result
print ("resultant list", str(res))
```

**Output:**

```py
initial dictionary [1, 2, 3, 4, None, 76, None, None, None]
resultant list [1, 2, 3, 4, None, 76]

```

**方法四:使用列举和列表理解**

```py
# Python code to demonstrate
# to remove trailing None
# elements from lists

# initialising lists
ini_list = [1, 2, 3, 4, None, 76, None, None, None]

# printing initial dictionary
print ("initial dictionary", str(ini_list))

# code toremove trailing None values
# from lists
res = [x for n, x in enumerate(ini_list)
       if any(y is not None for y in ini_list[n:])]

# printing result
print ("resultant list", str(res))
```

**Output:**

```py
initial dictionary [1, 2, 3, 4, None, 76, None, None, None]
resultant list [1, 2, 3, 4, None, 76]

```