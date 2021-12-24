# Python 程序设计一个无偏掷骰子函数

> 原文:[https://www . geesforgeks . org/python-程序到设计-一个无偏的掷骰子函数/](https://www.geeksforgeeks.org/python-program-to-design-an-unbiased-dice-throw-function/)

任务是编写一个 Python 程序来生成一个不偏不倚的骰子投掷并给出相应的输出。为此，我们可以使用 python *随机*模块中的各种方法。

**接近:**

*   使用 random.choice()方法
*   使用 random.randrange()方法
*   使用 random.randint()方法
*   使用 random.random()方法

**方法 1:** 使用[随机选择()](https://www.geeksforgeeks.org/python-numbers-choice-function/)

*选项()*是*随机*模块中的一个方法，它从列表、元组或字符串中返回一个随机项。这种方法是为从容器中获取随机数的特定目的而设计的，因此是实现从列表中获取随机数这一任务的最常见方法。

> **语法:**随机选择(序列)
> 
> **参数:**
> 
> *   **序列**是一个强制参数，可以是列表、元组或字符串。
> 
> **返回:**选项()返回随机项目。

现在，我们知道骰子的数字范围是 1-6，所以我们将给出[1，2，3，4，5，6]作为函数中的序列，函数将给出无偏的骰子投掷作为输出。以下是基于上述解释的实现:

## 蟒蛇 3

```
# Python program to design an unbiased dice throw 
# function

# Importing random library
import random

# Function to give an unbiased dice throw
def dice_throw():

    # Declaring the sequence
    sequence = [1, 2, 3, 4, 5, 6]

    # Printing the random result
    print(random.choice(sequence))

# Driver Code
# Calling the function
dice_throw()

# Calling the function
dice_throw()

# Calling the function
dice_throw()
```

**输出:**

```
3
1
4
```

**方法 2:** 使用[随机范围()](https://www.geeksforgeeks.org/randrange-in-python/)

这个方法用来生成一个范围内的随机数，对于列表，我们可以指定范围为 0 到它的长度，并得到索引，然后对应数值。这也提供了获得均匀放置的元素或某些倍数索引的元素的选项。

> **语法:** random.randrange(开始(选择)、停止、步进(选择))
> 
> **参数:**
> 
> *   **开始(opt) :** 发电考虑数由此开始，默认值为 0。此参数是可选的。
> *   **停止:**生成小于这个的数字。此参数是必需的。
> *   **步(选择):**范围的步点，不包括在内。这是可选的。默认值为 1。
> 
> **返回值:**该函数生成序列开始-停止跳过步骤中的数字。

现在，我们知道骰子有 1-6(含 1-6)范围内的数字，所以我们将给出[1，2，3，4，5，6]作为函数中的序列，然后使用 *randrange()* 找到一个随机索引，因此函数将给出一个无偏的骰子投掷作为输出。以下是基于上述解释的实现:

## 蟒蛇 3

```
# Python program to design an unbiased dice throw 
# function

# Importing random library
import random

# Function to give an unbiased dice throw
def dice_throw():

    # Declaring the sequence
    sequence = [1, 2, 3, 4, 5, 6]

    # using random.randrange() to  
    # get a random index number  
    rand_idx = random.randrange(len(sequence))

    # Printing the random result
    print(sequence[rand_idx])

# Driver Code
# Calling the function
dice_throw()

# Calling the function
dice_throw()

# Calling the function
dice_throw()
```

**输出:**

```
3
1
3
```

**方法 3:** 使用 [random.randint()](https://www.geeksforgeeks.org/python-randint-function/)

还有一种生成随机数的方法，这也可以用来生成一个范围内的任何数字，然后使用该数字索引，我们可以找到相应索引处的值，就像上述技术一样。但它的不同之处在于，它需要 2 个范围的强制参数。

> **语法:** randint(开始，结束)
> 
> **参数:**
> 
> *   **(开始，结束):**两者都必须是整型值。
> 
> **返回:**包括端点在内的[开始，结束]范围内的随机整数。

现在，我们知道骰子有 1-6(包括 1-6)范围内的数字，所以我们将给出[1，2，3，4，5，6]作为函数中的序列，然后使用 *randint()* 找到一个随机索引，因此函数将给出一个无偏的骰子投掷作为输出。以下是基于上述解释的实现:

## 蟒蛇 3

```
# Python program to design an unbiased dice throw 
# function

# Importing random library
import random

# Function to give an unbiased dice throw
def dice_throw():

    # Declaring the sequence
    sequence = [1, 2, 3, 4, 5, 6]

    # using random.randint() to  
    # get a random index number  
    rand_idx = random.randint(0, len(sequence)-1)

    # Printing the random result
    print(sequence[rand_idx])

# Driver Code
# Calling the function
dice_throw()

# Calling the function
dice_throw()

# Calling the function
dice_throw()
```

**输出:**

```
1
5
4
```

**方法 4:** 使用 [random.random()](https://www.geeksforgeeks.org/random-random-function-in-python/)

此方法生成 0 到 1 范围内的浮点数。我们还可以使用这个函数通过将结果相乘，然后类型转换为 int 来获得整数索引，然后获得相应的列表值，从而获得列表的索引值。然后我们将使用该索引值从列表中打印一个随机数。

> **语法:** random.random()
> 
> **参数:**此方法不接受任何参数。
> 
> **返回:**这个方法返回一个 0 到 1 之间的随机浮点数。

## 蟒蛇 3

```
# Python program to design an unbiased dice throw 
# function

# Importing random library
import random

# Function to give an unbiased dice throw
def dice_throw():

    # Declaring the sequence
    sequence = [1, 2, 3, 4, 5, 6]

    # using random.random() to  
    # get a random number  
    rand_idx = int(random.random() * len(sequence)) 

    # Printing the random result
    print(sequence[rand_idx])

# Driver Code
# Calling the function
dice_throw()

# Calling the function
dice_throw()

# Calling the function
dice_throw()
```

**输出:**

```
2
6
1
```