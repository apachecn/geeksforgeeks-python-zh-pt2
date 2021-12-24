# Python 中的 random.shuffle()函数

> 原文:[https://www . geesforgeks . org/random-shuffle-function-in-python/](https://www.geeksforgeeks.org/random-shuffle-function-in-python/)

`**sample()**`是`random`模块的内置方法。它用于打乱序列(列表)。洗牌意味着改变序列元素的位置。这里，洗牌操作正在进行。

## random.shuffle()

> **语法:** random.shuffle(序列，函数)
> 
> **参数:**
> 顺序:可以是列表
> 功能:可选，默认为随机()。它应该返回一个 0 到 1 之间的值。
> 
> **返回:**无

**示例 1 :** 重排列表

```py
# import the random module
import random

# declare a list
sample_list = ['A', 'B', 'C', 'D', 'E']

print("Original list : ")
print(sample_list)

# first shuffle 
random.shuffle(sample_list)
print("\nAfter the first shuffle : ")
print(sample_list)

# second shuffle
random.shuffle(sample_list)
print("\nAfter the second shuffle : ")
print(sample_list)
```

**输出:**

```py
Original list : 
['A', 'B', 'C', 'D', 'E']

After the first shuffle : 
['A', 'B', 'E', 'C', 'D']

After the second shuffle : 
['C', 'E', 'B', 'D', 'A']
```

`shuffle()`方法不能用于洗牌不可变的数据类型，如字符串。

**例 2:**

```py
# import the random module
import random

# user defined function to shuffle
def sample_function():
    return 0.5

sample_list = ['A', 'B', 'C', 'D', 'E']
print("Original list : ")
print(sample_list)

# as sample_function returns the same value
# each time, the order of shuffle will be the
# same each time
random.shuffle(sample_list, sample_function)
print("\nAfter the first shuffle : ")
print(sample_list)

sample_list = ['A', 'B', 'C', 'D', 'E']

random.shuffle(sample_list, sample_function)
print("\nAfter the second shuffle : ")
print(sample_list)
```

**输出:**

```py
Original list : 
['A', 'B', 'C', 'D', 'E']

After the first shuffle : 
['A', 'D', 'B', 'E', 'C']

After the second shuffle : 
['A', 'D', 'B', 'E', 'C']

```