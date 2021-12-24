# Python–洗牌字典值

> 原文:[https://www . geesforgeks . org/python-shuffle-dictionary-values/](https://www.geeksforgeeks.org/python-shuffle-dictionary-values/)

给定一个字典，任务是编写一个 python 程序，将它的值随机分配给不同的键。

**示例:**

> **输入:**test _ dict = {“gfg”:1、“is”:7、“best”:8、“for”:3、“极客”:9}
> 
> **输出:**{“gfg”:9、“is”:8、“best”:7、“for”:3、“极客”:1}
> 
> **说明:**键在同一个位置，但值被打乱。
> 
> **输入:**test _ dict = {“gfg”:7、“is”:1、“best”:8、“for”:3、“极客”:9}
> 
> **输出:**{“gfg”:9、“is”:8、“best”:7、“for”:3、“极客”:1}
> 
> **说明:**键在同一个位置，但值被打乱。

**方法#1:使用** [**洗牌()**](https://www.geeksforgeeks.org/random-shuffle-function-in-python/)**+**[**zip()**](https://www.geeksforgeeks.org/zip-in-python/)**+**[**dict()**](https://www.geeksforgeeks.org/python-set-4-dictionary-keywords-python/)

在这种情况下，我们使用 *shuffle()* 执行元素洗牌的任务，并且 *zip()* 用于将洗牌后的值映射到键。最后，使用 *dict()* 将结果转换为字典。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Shuffle dictionary Values
# Using shuffle() + zip() + dict()
import random

# initializing dictionary
test_dict = {"gfg": 1, "is": 7, "best": 8, 
             "for": 3, "geeks": 9}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# shuffling values
temp = list(test_dict.values())
random.shuffle(temp)

# reassigning to keys
res = dict(zip(test_dict, temp))

# printing result
print("The shuffled dictionary : " + str(res))
```

**输出:**

> 最初的字典是:{'gfg': 1，' is': 7，' best': 8，' for': 3，' geeks': 9}
> 
> 洗牌词典:{“gfg”:1，“is”:7，“best”:3，“for”:9，“geeks”:8 }

**方法 2:使用** [**样本()**](https://www.geeksforgeeks.org/python-random-sample-function/)**+**[**zip()**](https://www.geeksforgeeks.org/zip-in-python/)

在这种情况下，使用*随机*库的*样本()*来完成混洗值的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Shuffle dictionary Values
# Using sample() + zip()
from random import sample

# initializing dictionary
test_dict = {"gfg": 1, "is": 7, "best": 8, 
             "for": 3, "geeks": 9}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# reassigning to keys
res = dict(zip(test_dict, sample(list(test_dict.values()), 
                                 len(test_dict))))

# printing result
print("The shuffled dictionary : " + str(res))
```

**输出:**

> 最初的字典是:{'gfg': 1，' is': 7，' best': 8，' for': 3，' geeks': 9}
> 
> 洗牌词典:{'gfg': 8，' is': 9，' best': 1，' for': 3，' geeks': 7}