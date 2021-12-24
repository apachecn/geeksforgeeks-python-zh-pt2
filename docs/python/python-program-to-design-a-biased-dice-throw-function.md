# Python 程序设计的一个偏向骰子投掷功能

> 原文:[https://www . geeksforgeeks . org/python-程序到设计-一个偏向骰子投掷的函数/](https://www.geeksforgeeks.org/python-program-to-design-a-biased-dice-throw-function/)

在本文中，任务是编写一个 Python 程序来生成一个不偏不倚的骰子投掷并给出相应的输出。为此，我们可以使用 Python 随机库中的各种方法。

**接近:**

*   使用 random.choice()方法
*   使用 random.randrange()方法
*   使用 random.randint()方法
*   使用 random.random()方法
*   使用 random.choices()方法

#### **方法一:使用** [**随机选择()**](https://www.geeksforgeeks.org/python-numbers-choice-function/)

Choice()是 Python 编程语言中的一个内置函数，它从列表、元组或字符串中返回一个随机项。这种方法是为从容器中获取随机数的特定目的而设计的，因此是实现从列表中获取随机数这一任务的最常见方法。

> **语法:**随机选择(序列)
> 
> **参数:**
> 
> *   Sequence 是一个强制参数，可以是列表、元组或字符串。
> 
> **返回:**选项()返回随机项目。

现在，我们知道骰子有 1-6 范围内的数字，我们想要一个有偏差的结果作为输出，所以我们将给出[1，1，1，2，3，3，4，5，6，6，6，6]，因为函数中的序列和函数将给出一个有偏差的骰子投掷作为输出，因为数字的频率不一样。以下是基于上述解释的实现:

## 蟒蛇 3

```py
# Python program to design a biased dice throw 
# function

# Importing random library
import random

# Function to give a biased dice throw
def dice_throw():

    # Declaring the sequence
    sequence = [1, 1, 1, 2, 3, 3, 4, 5, 6, 6, 6, 6]

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

```py
6
3
6
```

#### 方法二:使用[random . range()](https://www.geeksforgeeks.org/randrange-in-python/)

这个方法用来生成一个范围内的随机数，对于列表，我们可以指定范围为 0 到它的长度，并得到索引，然后对应数值。这也提供了获得均匀放置的元素或某个倍数索引的元素的选项。

> **语法:** random.randrange(开始(选择)、停止、步进(选择))
> 
> **参数:**
> 
> *   **开始(opt) :** 发电考虑数由此开始，默认值为 0。此参数是可选的。
> *   **停止:**生成小于这个的数字。此参数是必需的。
> *   **步(选择):**范围的步点，不包括在内。这是可选的。默认值为 1。
> 
> **返回值:**该函数生成序列开始-停止跳过步骤中的数字。

现在，我们知道骰子有 1-6 范围内的数字，我们想要一个有偏的结果作为输出，所以我们将给出[1，1，1，2，3，3，4，5，6，6，6，6，6]作为函数中的序列，然后使用 randrange 找到一个随机索引，因此函数将给出一个有偏的骰子投掷作为输出。以下是基于上述解释的实现:

## 蟒蛇 3

```py
# Python program to design a biased dice throw 
# function

# Importing random library
import random

# Function to give a biased dice throw
def dice_throw():

    # Declaring the sequence
    sequence = [1, 1, 1, 2, 3, 3, 4, 5, 6, 6, 6, 6]

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

```py
6
3
3
```

#### 方法三:使用[randint random()](https://www.geeksforgeeks.org/python-randint-function/)

还有一种生成随机数的方法，也可以用来生成一个范围内的任意一个数，然后利用这个数的索引，我们就可以在对应的索引处找到这个值，就像上面提到的技术一样。但它的不同之处在于，它需要 2 个范围的强制参数。

> **语法:** randint(开始，结束)
> 
> **参数:**
> 
> *   **(开始，结束):**两者都必须是整型值。
> 
> **返回:**包括端点在内的[开始，结束]范围内的随机整数。

现在，我们知道骰子有 1-6 范围内的数字，我们想要一个有偏的结果作为输出，所以我们将给出[1，1，1，2，3，3，4，5，6，6，6，6，6]作为函数中的序列，然后使用 randint 找到一个随机索引，因此函数将给出一个有偏的骰子投掷作为输出。以下是基于上述解释的实现:

## 蟒蛇 3

```py
# Python program to design a biased dice throw 
# function

# Importing random library
import random

# Function to give a biased dice throw
def dice_throw():

    # Declaring the sequence
    sequence = [1, 1, 1, 2, 3, 3, 4, 5, 6, 6, 6, 6]

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

```py
5
2
4
```

#### 方法四:使用 [random.random()](https://www.geeksforgeeks.org/random-random-function-in-python/)

此方法生成 0 到 1 范围内的浮点数。我们还可以使用这个函数通过将结果相乘，然后类型转换为 int 来获得整数索引，然后获得相应的列表值，从而获得列表的索引值。然后我们将使用该索引值从列表中打印一个随机数。

> **语法:** random.random()
> 
> **参数:**此方法不接受任何参数。
> 
> **返回:**这个方法返回一个 0 到 1 之间的随机浮点数。

现在，我们知道骰子有 1-6 范围内的数字，我们想要一个有偏的结果作为输出，所以我们将给出[1，1，1，2，3，3，4，5，6，6，6，6，6]作为函数中的序列，然后使用 random 找到一个随机索引，因此函数将给出一个有偏的骰子投掷作为输出。以下是基于上述解释的实现:

## 蟒蛇 3

```py
# Python program to design a biased dice throw 
# function

# Importing random library
import random

# Function to give a biased dice throw
def dice_throw():

    # Declaring the sequence
    sequence = [1, 1, 1, 2, 3, 3, 4, 5, 6, 6, 6, 6]

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

```py
6
2
6
```

#### 方法 5:使用[随机选择()](https://www.geeksforgeeks.org/random-choices-method-in-python/)

choices()方法通过替换从列表中返回多个随机元素。您可以使用权重参数或累计权重参数来衡量每个结果的可能性。元素可以是字符串、范围、列表、元组或任何其他类型的序列。

> **语法:**随机选择(序列，权重=无，cum _ weights =无，k=1)
> 
> **参数:**
> 
> *   **序列:**它是一个强制参数，可以是列表、元组或字符串。
> *   **权重:**是一个可选参数，用于衡量每个值的可能性。
> *   **cum_weights:** 这是一个可选参数，用于对每个值的可能性进行加权，但在这种情况下，可能性是累积的
> *   **k:** 是一个可选参数，用于定义返回列表的长度。

现在，我们知道骰子有 1-6 个数字，所以我们将给出[1，2，3，4，5，6]作为一个序列，然后我们将设置列表中每个元素的权重。然后我们将打印输出。以下是基于上述解释的实现:

## 蟒蛇 3

```py
# Python program to design a biased dice throw 
# function

# Importing random library
import random

# Function to give a biased dice throw
def dice_throw():

    # Declaring the sequence
    sequence = [1, 2, 3, 4, 5, 6]

    # using random.choices() to  
    # get a random choice
    rand_choice = random.choices(sequence, weights = [1, 2, 3, 4, 5, 6], k = 1)

    # Printing the random result
    print(*rand_choice)

# Driver Code
# Calling the function
dice_throw()1
6
3

# Calling the function
dice_throw()

# Calling the function
dice_throw()
```

**输出:**

```py
1
6
3
```