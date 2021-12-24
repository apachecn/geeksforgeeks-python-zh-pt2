# Python–键的最大字符串值长度

> 原文:[https://www . geesforgeks . org/python-最大字符串值-密钥长度/](https://www.geeksforgeeks.org/python-maximum-string-value-length-of-key/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要找到特定键的所有字符串值的最大长度。这个问题可能发生在日常编程和 web 开发领域。让我们讨论执行这项任务的某些方法。

**示例–**

> **输入:**
> test _ list =[{'key1 ':' ABCD '，' key2' : 2}，{ ' key 1 ':' qwertyui '，' key2' : 2}，{ ' key 1 ':' xcvz '，' key3' : 3}，{ ' key 1 ':无，' key3' : 4}]
> 
> **输出:** 8
> **说明:**在所有给定键的值中*`key1`****qwertyui***的长度最大(为 8)。

**方法一:使用`max() + len()` +列表理解**
以上功能的组合可以解决这个问题。在本文中，我们使用 max()和 len()计算最大字符串长度。与每一个的比较都受到列表理解的限制。

```py
# Python3 code to demonstrate working of 
# Maximum String value length of Key
# Using max() + len() + list comprehension

# initializing list
test_list = [{'Gfg' :  "abcd", 'best' : 2}, 
             {'Gfg' :  "qwertyui", 'best' : 2},
             {'Gfg' :  "xcvz", 'good' : 3},
             {'Gfg' : None, 'good' : 4}]

# printing original list
print("The original list is : " + str(test_list))

# initializing Key 
filt_key = 'Gfg'

# Maximum String value length of Key
# Using max() + len() + list comprehension
temp = (sub[filt_key] for sub in test_list)
res = max(len(ele) for ele in temp if ele is not None)

# printing result 
print("The maximum length key value : " + str(res)) 
```

**Output :**

> 原始列表为:[{'best': 2，' Gfg': 'abcd'}，{'best': 2，' Gfg': 'qwertyui'}，{'good': 3，' Gfg': 'xcvz'}，{'good': 4，' Gfg': None}]
> 最大长度键值:8

**方法 2:使用列表理解+ `len() + max()`(一个 liner)**
类似的任务也可以组合在一行执行，进行紧凑求解。

```py
# Python3 code to demonstrate working of 
# Maximum String value length of Key
# Using max() + len() + list comprehension (one liner)

# initializing list
test_list = [{'Gfg' :  "abcd", 'best' : 2}, 
             {'Gfg' :  "qwertyui", 'best' : 2},
             {'Gfg' :  "xcvz", 'good' : 3},
             {'Gfg' : None, 'good' : 4}]

# printing original list
print("The original list is : " + str(test_list))

# initializing Key 
filt_key = 'Gfg'

# Maximum String value length of Key
# Using max() + len() + list comprehension (one liner)
res = len(max(test_list, key = lambda sub: len(sub[filt_key])
                if sub[filt_key] is not None else 0)[filt_key])

# printing result 
print("The maximum length key value : " + str(res)) 
```

**Output :**

> 原始列表为:[{'best': 2，' Gfg': 'abcd'}，{'best': 2，' Gfg': 'qwertyui'}，{'good': 3，' Gfg': 'xcvz'}，{'good': 4，' Gfg': None}]
> 最大长度键值:8