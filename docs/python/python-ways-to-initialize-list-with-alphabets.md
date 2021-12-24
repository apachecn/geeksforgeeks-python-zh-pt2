# Python |用字母初始化列表的方法

> 原文:[https://www . geesforgeks . org/python-用字母初始化列表的方法/](https://www.geeksforgeeks.org/python-ways-to-initialize-list-with-alphabets/)

在处理列表时，有时我们希望用英文字母 a-z 初始化列表。这在竞争性编程和某些应用程序中是一个必不可少的工具。让我们讨论实现这一点的各种方法。

**方法#1:天真的方法**
我们脑海中出现的最普遍的方法是使用蛮力方法，运行一个循环直到 26，并在添加列表中的字母时递增它。

```py
# Python3 code to demonstrate 
# Filling alphabets
# using naive method 

# initializing empty list 
test_list = []

# printing initial list 
print ("Initial list : " + str(test_list))

# using naive method
# for filling alphabets
alpha = 'a'
for i in range(0, 26):
    test_list.append(alpha)
    alpha = chr(ord(alpha) + 1) 

# printing resultant list 
print ("List after insertion : " + str(test_list))
```

**输出:**

> 初始列表:[]
> 插入后的列表:['a '，' b '，' c '，' d '，' e '，' f '，' g '，' h '，' I '，' j '，' k '，' l '，' m '，' n '，' o '，' p '，' q '，' r '，' s '，' t '，' u '，' v '，' w '，' x '，' y '，' z']

**方法 2:使用列表理解**
这是一种类似于上述方法的方法，但更像是天真方法的简写，因为它使用列表理解技术来完成任务。

```py
# Python3 code to demonstrate 
# Filling alphabets
# using list comprehension

# initializing empty list 
test_list = []

# printing initial list 
print ("Initial list : " + str(test_list))

# using list comprehension
# for filling alphabets
test_list = [chr(x) for x in range(ord('a'), ord('z') + 1)]

# printing resultant list 
print ("List after insertion : " + str(test_list))
```

**输出:**

> 初始列表:[]
> 插入后的列表:['a '，' b '，' c '，' d '，' e '，' f '，' g '，' h '，' I '，' j '，' k '，' l '，' m '，' n '，' o '，' p '，' q '，' r '，' s '，' t '，' u '，' v '，' w '，' x '，' y '，' z']

**方法三:使用`map()`**
使用`map()`是执行这个特殊任务的优雅方式。它将一个范围内的数字转换为特定的数据类型，在本例中为 char，并分配给列表。

```py
# Python3 code to demonstrate 
# Filling alphabets
# using map()

# initializing empty list 
test_list = []

# printing initial list 
print ("Initial list : " + str(test_list))

# using map()
# for filling alphabets
test_list = list(map(chr, range(97, 123)))

# printing resultant list 
print ("List after insertion : " + str(test_list))
```

**输出:**

> 初始列表:[]
> 插入后的列表:['a '，' b '，' c '，' d '，' e '，' f '，' g '，' h '，' I '，' j '，' k '，' l '，' m '，' n '，' o '，' p '，' q '，' r '，' s '，' t '，' u '，' v '，' w '，' x '，' y '，' z']

**方法#4:使用`string.ascii_lowercase`**
这种最腐解和最新的方式来执行这个特殊的任务。使用这个新的内置函数将在内部处理编码部分，为用户提供有用的速记。

```py
# Python3 code to demonstrate 
# Filling alphabets
# using string
import string

# initializing empty list 
test_list = []

# printing initial list 
print ("Initial list : " + str(test_list))

# using string 
# for filling alphabets
test_list = list(string.ascii_lowercase)

# printing resultant list 
print ("List after insertion : " + str(test_list))
```

**输出:**

> 初始列表:[]
> 插入后的列表:['a '，' b '，' c '，' d '，' e '，' f '，' g '，' h '，' I '，' j '，' k '，' l '，' m '，' n '，' o '，' p '，' q '，' r '，' s '，' t '，' u '，' v '，' w '，' x '，' y '，' z']