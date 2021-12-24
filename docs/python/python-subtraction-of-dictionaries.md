# Python |字典减法

> 原文:[https://www . geesforgeks . org/python-字典减法/](https://www.geeksforgeeks.org/python-subtraction-of-dictionaries/)

有时，在使用字典时，我们可能会遇到一个效用问题，即需要在字典的公共键之间执行基本操作。这可以扩展到要执行的任何操作。让我们在本文中讨论相似键值的减法和解决方法。

### **方法一:使用词典理解+按键()**

以上两者的结合可以用来执行这个特殊的任务。这只是较长循环方法的简写，可以用来在一行中执行此任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Subtraction of dictionaries
# Using dictionary comprehension + keys()

# Initialize dictionaries
test_dict1 = {'gfg' : 6, 'is' : 4, 'best' : 7}
test_dict2 = {'gfg' : 10, 'is' : 6, 'best' : 10}

# printing original dictionaries
print("The original dictionary 1 : " +  str(test_dict1))
print("The original dictionary 2 : " +  str(test_dict2))

# Using dictionary comprehension + keys()
# Subtraction of dictionaries
res = {key: test_dict2[key] - test_dict1.get(key, 0)
                       for key in test_dict2.keys()}

# printing result
print("The difference dictionary is : " + str(res))
```

**Output : **

```
The original dictionary 1 : {'gfg': 6, 'is': 4, 'best': 7}
The original dictionary 2 : {'gfg': 10, 'is': 6, 'best': 10}
The difference dictionary is : {'gfg': 4, 'is': 2, 'best': 3}
```

### **方法 2:使用计数器()+“-”运算符**

上述方法的组合可用于执行该特定任务。在这种情况下，Counter 函数将字典转换为减运算符可以执行减法任务的形式。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Subtraction of dictionaries
# Using Counter() + "-" operator
from collections import Counter
from collections import subtract

# Initialize dictionaries
test_dict1 = {'gfg' : 6, 'is' : 4, 'best' : 7}
test_dict2 = {'gfg' : 10, 'is' : 6, 'best' : 10}

# printing original dictionaries
print("The original dictionary 1 : " +  str(test_dict1))
print("The original dictionary 2 : " +  str(test_dict2))

# Using Counter() + "-" operator
# Subtraction of dictionaries
temp1 = Counter(test_dict1)
temp2 = Counter(test_dict2)
res = temp2 - temp1

# printing result
print("The difference dictionary is : " + str(dict(res)))

# Using the subtract method of 
test_dict2.subtract(test_dict1)

# printing result
print("The difference dictionary is : " + str(dict(test_dict2)))
```

**Output : **

```
                        The original dictionary 1 : {'gfg': 6, 'is': 4, 'best': 7}
                        The original dictionary 2 : {'gfg': 10, 'is': 6, 'best': 10}
                        The difference dictionary is : {'gfg': 4, 'is': 2, 'best': 3}
```