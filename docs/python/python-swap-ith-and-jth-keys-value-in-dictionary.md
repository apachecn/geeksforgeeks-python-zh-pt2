# Python–在字典中交换 ith 和 jth 键的值

> 原文:[https://www . geesforgeks . org/python-swap-ith-and-jth-key-value in dictionary/](https://www.geeksforgeeks.org/python-swap-ith-and-jth-keys-value-in-dictionary/)

给定一个字典，执行 ith 和 jth 索引键值的交换。

> **输入**:test _ dict = {“Gfg”:2、“is”:4、“best”:7、“for”:9、“极客”:10}、I、j = 1、4
> **输出**:{“Gfg”:2、“is”:10、“best”:7、“for”:9、“极客”:4}
> **解释**:价值观的“is”和“极客”对调。
> 
> **输入**:test _ dict = {“Gfg”:2、“is”:4、“best”:7、“for”:9、“极客”:10}、I、j = 1、2
> **输出**:{“Gfg”:2、“is”:7、“best”:4、“for”:9、“极客”:10}
> **解释**:价值观的“is”和“best”对调。

**方法#1:使用循环+值()**

这是执行这项任务的方法之一。在这种情况下，我们获得所需交换键的值，并在循环中执行所需的交换，这将创建一个新的字典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Swap ith and jth key's value in dictionary
# Using loop + values()

# initializing dictionary
test_dict = {"Gfg": 2, "is": 4, "best": 7,
             "for": 9, "geeks": 10}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing i, j 
i, j = 1, 3

# Extracting keys 
vals = list(test_dict.values())

# performing swap 
vals[i], vals[j] = vals[j], vals[i]

# setting new values 
res = dict()
for idx, key in enumerate(test_dict):
    res[key] = vals[idx]

# printing result 
print("Required dictionary : " + str(res)) 
```

**输出:**

> 原词典为:{'Gfg': 2，' is': 4，' best': 7，' for': 9，' geeks': 10}
> 必选词典:{'Gfg': 2，' is': 9，' best': 7，' for': 4，' geeks': 10}

**方法 2:使用值()+字典理解**

这是执行这项任务的方法之一。这是一种类似于上面的方法，不同之处在于使用字典理解来执行字典分配步骤。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Swap ith and jth key's value in dictionary
# Using values() + dictionary comprehension

# initializing dictionary
test_dict = {"Gfg": 2, "is": 4, "best": 7, 
             "for": 9, "geeks": 10}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing i, j 
i, j = 1, 3

# Extracting keys 
vals = list(test_dict.values())

# performing swap 
vals[i], vals[j] = vals[j], vals[i]

# setting new values 
res = {key : vals[idx] for idx, key in enumerate(test_dict)}

# printing result 
print("Required dictionary : " + str(res)) 
```

**输出:**

> 原词典为:{'Gfg': 2，' is': 4，' best': 7，' for': 9，' geeks': 10}
> 必选词典:{'Gfg': 2，' is': 9，' best': 7，' for': 4，' geeks': 10}