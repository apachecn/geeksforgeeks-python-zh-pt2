# Python–反向字典键顺序

> 原文:[https://www . geesforgeks . org/python-reverse-dictionary-key-order/](https://www.geeksforgeeks.org/python-reverse-dictionary-keys-order/)

有时候，在使用字典时，我们会遇到一个问题，我们需要颠倒字典的顺序。这是一个非常常见的问题，可以应用于许多领域，包括日常编程和 web 开发。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`OrderedDict() + reversed() + items()`**
这个方法是针对旧版 Python 的。旧版本不能保持字典中的顺序，因此必须转换为 OrderedDict 来执行此任务。

```
# Python3 code to demonstrate working of 
# Reverse Dictionary Keys Order
# Using OrderedDict() + reversed() + items()
from collections import OrderedDict

# initializing dictionary
test_dict = {'gfg' : 4, 'is' : 2, 'best' : 5}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Reverse Dictionary Keys Order
# Using OrderedDict() + reversed() + items()
res = OrderedDict(reversed(list(test_dict.items())))

# printing result 
print("The reversed order dictionary : " + str(res)) 
```

**Output :**

> 原词典:{'is': 2，' best': 5，' gfg': 4}
> 逆序词典:OrderedDict([('gfg '，4)，(' best '，5)，(' is '，2)]