# 根据用户输入创建动态命名变量的 Python 程序

> 原文:[https://www . geesforgeks . org/python-程序-创建-动态命名-变量-来自用户输入/](https://www.geeksforgeeks.org/python-program-to-create-dynamically-named-variables-from-user-input/)

给定一个字符串输入，任务是编写一个 Python 程序，根据该输入创建一个变量(作为变量名)，并为其赋值。以下是根据用户输入创建动态命名变量的方法:

**方法 1:** 使用 [globals()](https://www.geeksforgeeks.org/python-globals-function/) 方法。

## 蟒蛇 3

```py
# Dynamic_Variable_Name can be
# anything the user wants
Dynamic_Variable_Name = "geek"

# The value 2020 is assigned
# to "geek" variable
globals()[Dynamic_Variable_Name] = 2020

# Display variable
print(geek)
```

**输出:**

```py
2020
```

**方法二:**采用[本地人()](https://www.geeksforgeeks.org/python-locals-function/)方法。

## 蟒蛇 3

```py
# Dynamic_Variable_Name can be
# anything the user wants.
Dynamic_Variable_Name = "geek"

# The value 2020 is assigned
# to "geek" variable
locals()[Dynamic_Variable_Name] = 2020

# Display variable
print(geek)
```

**输出:**

```py
2020
```

**方法 3:** 使用 [exec()](https://www.geeksforgeeks.org/exec-in-python/) 方法。

## 蟒蛇 3

```py
# Dynamic_Variable_Name can be
# anything the user wants.
Dynamic_Variable_Name = "geek"

# The value 2020 is assigned
# to "geek" variable
exec("%s = %d" % (Dynamic_Variable_Name, 2020))

# Display variable
print(geek)
```

**输出:**

```py
2020
```

**方法 4:** 使用 [vars()](https://www.geeksforgeeks.org/vars-function-python/) 方法

## 蟒蛇 3

```py
# Dynamic_Variable_Name can be
# anything the user wants.
Dynamic_Variable_Name = "geek"

# The value 2020 is assigned
# to "geek" variable
vars()[Dynamic_Variable_Name] = 2020

# Display variable
print(geek)
```

**输出:**

```py
2020
```