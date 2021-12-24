# Python |字典中改变键的方法

> 原文:[https://www . geeksforgeeks . org/python-更改字典中的键的方法/](https://www.geeksforgeeks.org/python-ways-to-change-keys-in-dictionary/)

给定一个字典，任务是根据需求改变关键字。让我们看看我们可以用不同的方法来完成这项任务。

**方法#1:使用幼稚的方法**

```py
# Python code to demonstrate
# changing keys of dictionary
# using naive method

# inititialising dictionary
ini_dict = {'nikhil': 1, 'vashu' : 5,
            'manjeet' : 10, 'akshat' : 15}

# printing initial json
print ("initial 1st dictionary", ini_dict)

# changing keys of dictionary
ini_dict['akash'] = ini_dict['akshat']
del ini_dict['akshat']

# printing final result
print ("final dictionary", str(ini_dict))
```

**Output:**

> 初始第一字典{'akshat': 15，' nikhil': 1，' manjeet': 10，' vashu': 5}
> 最终字典{'akash': 15，' nikhil': 1，' manjeet': 10，' vashu': 5}