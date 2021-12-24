# Python | yield 关键字

> 原文:[https://www.geeksforgeeks.org/python-yield-keyword/](https://www.geeksforgeeks.org/python-yield-keyword/)

**Yield** 是 Python 中的一个关键字，用于从函数返回而不破坏其局部变量的状态，当函数被调用时，执行从最后一条 Yield 语句开始。任何包含 yield 关键字的函数都称为生成器。因此，产量是制造发电机的要素。Python 中的 yield 关键字不太为人所知，但它有一个人们能想到的更大的效用。

**代码#1 :** 演示产量工作

## 蟒蛇 3

```py
# Python3 code to demonstrate
# yield keyword

# generator to print even numbers
def print_even(test_list) :
    for i in test_list:
        if i % 2 == 0:
            yield i

# initializing list
test_list = [1, 4, 5, 6, 7]

# printing initial list
print ("The original list is : " +  str(test_list))

# printing even numbers
print ("The even numbers in list are : ", end = " ")
for j in print_even(test_list):
    print (j, end = " ")
```

**输出:**

```py
The original list is : [1, 4, 5, 6, 7]
The even numbers in list are :  4 6 
```

**代码#2:**

## 蟒蛇 3

```py
# A Python program to generate squares from 1
# to 100 using yield and therefore generator

# An infinite generator function that prints
# next square number. It starts with 1
def nextSquare():
    i = 1

    # An Infinite loop to generate squares
    while True:
        yield i*i                
        i += 1 # Next execution resumes
                # from this point    

# Driver code
for num in nextSquare():
    if num > 100:
        break   
    print(num)
```

**输出:**

```py
1
4
9
16
25
36
49
64
81
100
```

**产量优势:**

*   由于它存储局部变量状态，因此控制了内存分配的开销。
*   由于保留了旧状态，流程不会从头开始，因此节省了时间。

**产量劣势:**

*   有时，如果函数调用处理不当，那么 yield 的使用就会出错。
*   时间和内存优化以代码的复杂性为代价，因此有时很难理解其背后的逻辑。

**实际应用:**
可能的实际应用是，当处理最后一批数据并从中搜索细节时，可以使用 yield，因为我们不需要从头再查找，因此可以节省时间。根据用例，可能会有许多应用程序。

## 蟒蛇 3

```py
# Python3 code to demonstrate yield keyword

# Checking number of occurrence of
# geeks in string

# generator to print even numbers
def print_even(test_string) :
    for i in test_string:
        if i == "geeks":
            yield i

# initializing string
test_string = " The are many geeks around you, \
              geeks are known for teaching other geeks"

# printing even numbers using yield
count = 0
print ("The number of geeks in string is : ", end = "" )
test_string = test_string.split()

for j in print_even(test_string):
    count = count + 1

print (count)
```

**输出:**

```py
The number of geeks in string is : 3
```