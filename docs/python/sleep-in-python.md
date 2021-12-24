# Python 中的 time.sleep()

> 原文:[https://www.geeksforgeeks.org/sleep-in-python/](https://www.geeksforgeeks.org/sleep-in-python/)

**Python time sleep()函数**暂停执行给定的秒数。

有时，需要停止程序的流程，以便可以执行其他几个程序，或者仅仅是因为需要实用程序。sleep()可以在这种情况下派上用场，它提供了一种精确而灵活的方法来停止任何时间段的代码流。这个函数讨论了这个函数的洞察力。

### **Python 时间睡眠()语法:**

> **语法:**睡眠(秒)
> 
> **参数:**
> 
> **秒:**要求代码停止的秒数。
> 
> **返回:** **VOID。**

## **Python 时间睡眠()方法示例**

### **例 1:** 演示睡眠的工作方式()

## 蟒蛇 3

```py
# Python code to demonstrate
# working of sleep()

import time

# printing the start time
print("The time of code execution begin is : ", end="")
print(time.ctime())

# using sleep() to hault the code execution
time.sleep(6)

# printing the end time
print("The time of code execution end is : ", end="")
print(time.ctime())
```

**输出:**

```py
The time of code execution begin is : Mon Apr  9 20:57:10 2018
The time of code execution end is : Mon Apr  9 20:57:16 2018
```

**应用:**

sleep()用于许多应用程序。这可以在 sleep()的帮助下实现。另一个流行的应用程序是使用 sleep()逐字母打印单词，以获得良好的用户界面。后者由下面的代码表示。

### **示例 2:** 演示 Python time.sleep 的应用(1)

## 蟒蛇 3

```py
# Python code to demonstrate
# application of sleep()

import time

# initializing string
strn = "GeeksforGeeks"

# printing geeksforgeeks after delay
# of each character
for i in range(0, len(strn)):
    print(strn[i], end="")
    time.sleep(2)
```

**输出:**

```py
GeeksForGeeks
```

**注:**睡眠的可见效果()可以在本地编辑器中看到。

### **示例 3:** 在**列表**中创建时间延迟

## 蟒蛇 3

```py
# importing time package
import time

# creating a time delay of 5 seconds
time.sleep(5)

# creating and Initializing a list
myList = ['Jai', 'Shree', 'RAM', 5, 'August', 2020]

# the list will be displayed after the
# delay of 5 seconds
print(myList)
```

**输出:**

延迟 5 秒后，我们将获得如下输出:

```py
['Jai', 'Shree', 'RAM', 5, 'August', 2020]
```

### **示例 4:** 在**元组**中创建时间延迟

## 蟒蛇 3

```py
# importing time package
import time

# creating a time delay of 4 seconds
time.sleep(4)

# creating and Initializing a tuple
mytuple = ('Anil Kumbl', 'Sachin Tendulkar', 'Sunil Gavaskar',
           'Rahul Dravid', 'Mahendra Singh Dhoni',
           'Dennis Lillee', 'Muttiah Muralitharan', 'Shane Warne')

# the tuple will be displayed after the delay of 4 seconds
print(mytuple)
```

**输出:**

延迟 4 秒后，我们将获得如下输出:

```py
('Anil Kumbl', 'Sachin Tendulkar', 'Sunil Gavaskar', 'Rahul Dravid',
'Mahendra Singh Dhoni', 'Dennis Lillee', 'Muttiah Muralitharan', 'Shane Warne')
```

### **示例 5:** 创建**多个**时间延迟

## 蟒蛇 3

```py
# importing time package
import time

# creating and Initializing a list
Languages = ['Java', 'C++', 'Python', 'Javascript', 'C#', 'C', 'Kotlin']

# creating a time delay of 5 seconds
time.sleep(5)

# the list will be displayed after the delay of 5 seconds
print(Languages)

for lan in Languages:

    # creating a time delay of 13 seconds
    time.sleep(13)

    # After every 13 seconds an item of list will be displayed
    print(lan)
```

**输出:**

延迟 5 秒后，列表将显示为:

```py
['Java', 'C++', 'Python', 'Javascript', 'C#', 'C', 'Kotlin']
```

然后，每隔 13 秒，列表中的项目将显示为:

```py
Java
C++
Python
Javascript
C#
C
Kotlin
```

### **示例 6:**列表理解中的**时间延迟**

## 蟒蛇 3

```py
# importing time package
import time

# creating and Initializing a list
cricketers = ['Anil Kumble', 'Sachin Tendulkar', 'Sunil Gavaskar',
              'Rahul Dravid', 'Mahendra Singh Dhoni',
              'Dennis Lillee', 'Muttiah Muralitharan', 'Shane Warne']

# time delay of 7 seconds is created
# after every 7 seconds item of list gets displayed
cricketers = [(time.sleep(7), print(cric)) for cric in cricketers]
```

**输出:**

每隔 7 秒钟，列表中的项目将显示为:

```py
Anil Kumble
Sachin Tendulkar
Sunil Gavaskar
Rahul Dravid
Mahendra Singh Dhoni
Dennis Lillee
Muttiah Muralitharan
Shane Warne
```

### **示例 7:** 在列表中创建 **3 分钟**的时间延迟

## 蟒蛇 3

```py
# importing time package
import time

# creating and Initializing a list
Languages = ['Java', 'C++', 'Python', 'Javascript',
             'C#', 'C', 'Kotlin']

# creating a time delay of 3 minutes
time.sleep(3 * 60)

# the list will be displayed after the delay
# of 3 minutes
print(Languages)
```

**输出:**

延迟 3 分钟后，列表将显示为:

```py
['Java', 'C++', 'Python', 'Javascript', 'C#', 'C', 'Kotlin']
```