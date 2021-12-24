# Python–字符串到子字符串

> 原文:[https://www.geeksforgeeks.org/python-string-till-substring/](https://www.geeksforgeeks.org/python-string-till-substring/)

有时，除了查找子字符串，我们可能还需要在找到子字符串之前获取正在出现的字符串。让我们讨论执行这项任务的某些方法。

### **方法#1:使用分区()**

分区函数可以用来执行这个任务，在这个任务中，我们只返回出现在分区字之前的那部分分区。

## 蟒蛇 3

```
# Python3 code to demonstrate
# String till Substring
# using partition()

# initializing string
test_string = "GeeksforGeeks is best for geeks"

# initializing split word
spl_word = 'best'

# printing original string
print("The original string : " + str(test_string))

# printing split string
print("The split string : " + str(spl_word))

# using partition()
# String till Substring
res = test_string.partition(spl_word)[0]

# print result
print("String before the substring occurrence : " + res)
```

**Output : **

```
The original string : GeeksforGeeks is best for geeks
The split string : best
String before the substring occurrence : GeeksforGeeks is
```

### 
**方法 2:使用 split()**

拆分函数也可以应用于执行这个特定的任务，在这个函数中，我们使用限制拆分的能力，然后打印前一个字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate
# String till Substring
# using split()

# initializing string
test_string = "GeeksforGeeks is best for geeks"

# initializing split word
spl_word = 'best'

# printing original string
print("The original string : " + str(test_string))

# printing split string
print("The split string : " + str(spl_word))

# using split()
# String till Substring
res = test_string.split(spl_word)[0]

# print result
print("String before the substring occurrence : " + res)
```

**Output : **

```
The original string : GeeksforGeeks is best for geeks
The split string : best
String before the substring occurrence : GeeksforGeeks is
```