# Python 无关键字

> 原文:[https://www.geeksforgeeks.org/python-none-keyword/](https://www.geeksforgeeks.org/python-none-keyword/)

无用于定义空值。它与空字符串、False 或零不同。它是类非分类型对象的数据类型。

为变量赋值“无”是将变量重置为其原始空状态的一种方法。

**例 1:**

## 蟒蛇 3

```py
# we will check the type of None
print(type(None))
```

**Output**

```py
<class 'NoneType'>

```

**例 2:**

## 蟒 3

```py
# declaring a variable as None
var = None

# checking it's value
if var is None:
    print("var has a value of None")
else:
    print("var has a value")
```

**输出**

```py
var has a value of None

```

**注意:**如果一个函数没有返回任何东西，那么它在 python 中返回 None。