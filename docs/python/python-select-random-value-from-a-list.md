# Python |从列表中选择随机值

> 原文:[https://www . geesforgeks . org/python-从列表中选择随机值/](https://www.geeksforgeeks.org/python-select-random-value-from-a-list/)

在游戏或各种类型的赌博等的日常编程中，生成随机数一直是一个有用的工具。因此，任何编程语言的知识和人手不足总是一个优势。

让我们讨论从列表中选择随机值的所有不同方法。

**方法#1 :** 使用`[random.choice()](https://www.geeksforgeeks.org/python-numbers-choice-function/)`

该方法是为从容器中获取随机数的特定目的而设计的，因此是实现从列表中获取随机数这一任务的最常见方法。

```
# Python3 code to demonstrate 
# to get random number from list
# using random.choice()
import random

# initializing list 
test_list = [1, 4, 5, 2, 7]

# printing original list 
print ("Original list is : " + str(test_list))

# using random.choice() to 
# get a random number 
random_num = random.choice(test_list)

# printing random number
print ("Random selected number is : " + str(random_num))
```

**Output:**

```
Original list is : [1, 4, 5, 2, 7]
Random selected number is : 1

```

**方法 2 :** 使用`[random.randrange()](https://www.geeksforgeeks.org/randrange-in-python/)`

这个方法用来生成一个范围内的随机数，对于列表，我们可以指定范围为 0 到它的长度，并得到索引，然后对应数值。这也提供了获得均匀放置的元素或特定倍数索引的元素的选项。

```
# Python3 code to demonstrate 
# to get random number from list
# using random.randrange
import random

# initializing list 
test_list = [1, 4, 5, 2, 7]

# printing original list 
print ("Original list is : " + str(test_list))

# using random.randrange() to 
# get a random number 
rand_idx = random.randrange(len(test_list))
random_num = test_list[rand_idx]

# printing random number
print ("Random selected number is : " + str(random_num))
```

**Output:**

```
Original list is : [1, 4, 5, 2, 7]
Random selected number is : 7

```

**方法 3 :** 使用`[random.randint()](https://www.geeksforgeeks.org/python-randint-function/)`

还有一种生成随机数的方法，这也可以用来生成一个范围内的任何数字，然后使用该数字索引，我们可以找到相应索引处的值，就像上述技术一样。但它的不同之处在于，它需要 2 个范围的强制参数。

```
# Python3 code to demonstrate 
# to get random number from list
# using random.randint()
import random

# initializing list 
test_list = [1, 4, 5, 2, 7]

# printing original list 
print ("Original list is : " + str(test_list))

# using random.randint() to 
# get a random number 
rand_idx = random.randint(0, len(test_list)-1)
random_num = test_list[rand_idx]

# printing random number
print ("Random selected number is : " + str(random_num))
```

**Output:**

```
Original list is : [1, 4, 5, 2, 7]
Random selected number is : 4

```

**方法 4:使用`random.random()`**

此方法生成 0 到 1 范围内的浮点数。我们还可以使用这个函数通过将结果相乘，然后类型转换为 int 来获得整数索引，然后获得相应的列表值，从而获得列表的索引值。

```
# Python3 code to demonstrate 
# to get random number from list
# using random.random()
import random

# initializing list 
test_list = [1, 4, 5, 2, 7]

# printing original list 
print ("Original list is : " + str(test_list))

# using random.random() to 
# get a random number 
rand_idx = int(random.random() * len(test_list))
random_num = test_list[rand_idx]

# printing random number
print ("Random selected number is : " + str(random_num))
```

**Output:**

```
Original list is : [1, 4, 5, 2, 7]
Random selected number is : 7

```