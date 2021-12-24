# Python |拆分单个整数的列表

> 原文:[https://www . geesforgeks . org/python-split-a-list-having-single-integer/](https://www.geeksforgeeks.org/python-split-a-list-having-single-integer/)

给定一个包含单个整数的列表，任务是拆分列表中的每个值。

**示例:**

```py
Input: Input = [23]
Output: Output  = [2, 3]

Input: Input = [15478]
Output: Output  = [1, 5, 4, 7, 8]

```

**方法#1:使用地图**

```py
# Python code to split list containing single integer

# List initialization
input = [200]

# Using map
output = list(map(int, str(input[0])))

# Printing output
print(output)
```

**Output:**

```py
[2, 0, 0]

```

**方法 2:使用列表理解**

```py
# Python code to split list containing single integer

# List initialization
input = [231]

# Using list comprehension
output = [int(x) if x.isdigit() else x 
          for z in input for x in str(z)]

# Printing output
print(output)
```

**Output:**

```py
[2, 3, 1]

```

**方法 3:使用循环**

```py
# Python code to split list containing single integer

# List initialization
input = [987]

# Converting to int
input = int(input[0])

# Output list initialization
output = []

while input>0:
    rem = input % 10
    input = int(input / 10)
    output.append(rem)

# Printing output
print(output)
```

**Output:**

```py
[7, 8, 9]

```