# Python 程序将列表转换为字符串

> 原文:[https://www . geesforgeks . org/python-program-to-convert-a-list-to-string/](https://www.geeksforgeeks.org/python-program-to-convert-a-list-to-string/)

给定一个列表，编写一个 Python 程序将给定的列表转换为字符串。

当给定一个列表并将其转换为字符串时，我们可能会遇到各种情况。例如，从字符串列表或整数列表转换为字符串。

**示例:**

```
Input: ['Geeks', 'for', 'Geeks']
Output: Geeks for Geeks

Input: ['I', 'want', 4, 'apples', 'and', 18, 'bananas']
Output: I want 4 apples and 18 bananas
```

让我们看看将列表转换为字符串的各种方法。

**方法#1:**
遍历列表，并在某个空字符串中不断为每个索引添加元素。

```
# Python program to convert a list to string

# Function to convert  
def listToString(s): 

    # initialize an empty string
    str1 = "" 

    # traverse in the string  
    for ele in s: 
        str1 += ele  

    # return string  
    return str1 

# Driver code    
s = ['Geeks', 'for', 'Geeks']
print(listToString(s)) 
```

**Output:**

```
GeeksforGeeks

```

**方法 2:使用。join()方法**

```
# Python program to convert a list
# to string using join() function

# Function to convert  
def listToString(s): 

    # initialize an empty string
    str1 = " " 

    # return string  
    return (str1.join(s))

# Driver code    
s = ['Geeks', 'for', 'Geeks']
print(listToString(s)) 
```

**Output:**

```
Geeks for Geeks

```

但是如果列表同时包含字符串和整数作为其元素呢？在这些情况下，上面的代码不起作用。我们需要在添加到字符串时将其转换为字符串。

**方法三:使用列表理解**

```
# Python program to convert a list
# to string using list comprehension

s = ['I', 'want', 4, 'apples', 'and', 18, 'bananas']

# using list comprehension
listToStr = ' '.join([str(elem) for elem in s])

print(listToStr) 
```

**Output:**

```
I want 4 apples and 18 bananas

```

**方法#4:使用 map()**
使用 map()方法将字符串(用于将列表中的元素转换为字符串)与给定的迭代器、列表进行映射。

```
# Python program to convert a list
# to string using list comprehension

s = ['I', 'want', 4, 'apples', 'and', 18, 'bananas']

# using list comprehension
listToStr = ' '.join(map(str, s))

print(listToStr) 
```

**Output:**

```
I want 4 apples and 18 bananas

```