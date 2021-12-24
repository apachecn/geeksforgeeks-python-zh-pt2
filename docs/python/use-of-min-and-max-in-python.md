# Python 中 min()和 max()的使用

> 原文:[https://www.geeksforgeeks.org/use-of-min-and-max-in-python/](https://www.geeksforgeeks.org/use-of-min-and-max-in-python/)

先决条件:[Python 中的 min()max()](https://www.geeksforgeeks.org/max-min-python/)
我们来看一些关于 min()和 max()函数的有趣事实。这些函数用于计算参数中传递的值的最大值和最小值。或者，当我们传递字符串或字符串列表作为参数时，它分别给出字典序最大值和字典序最小值。

## 蟒蛇 3

```
l= ["ab", "abc", "abd", "b"]

l1="abc"

# prints 'b'
print(max(l))

# prints 'ab'
print(min(l))

#prints 'c'
print(max(l1))

#prints 'a'
print(min(l1))
```

这里你注意到输出是按照字典顺序来的。但是我们也可以根据字符串的长度或者根据我们的要求通过简单地传递函数名或者 lambda 表达式来找到输出。
**参数:**
默认情况下，min()和 max()不需要任何额外的参数。但是，它有一个可选参数:

> **键**–用作最小/最大比较键的功能

> **语法:** max(x1，x2，…，xn，key=function_name)
> 这里是 x1，x2，x3..，xn 传递了参数
> **function_name :** 表示要对这些参数执行哪种类型的操作。让 function_name=len，那么现在输出根据 x1，x2 的长度给出..，xn。

**返回值:**

> 它根据传递的参数返回列表的最大值或最小值。

## 蟒蛇 3

```
# Python code explaining min() and max()
l = ["ab", "abc", "bc", "c"]

print(max(l, key = len))
print(min(l, key = len))
```

**Output:** 

```
abc
c
```

**解释:**
在上面的程序中，max()函数取两个参数 **:** l(list)和 key = len(function_name)。这个 key = len(function_name)函数在比较之前转换每个元素，它取值并返回 1 个值，然后在 max()或 min()内使用该值来代替原始值。这里 key 把列表的每个元素转换成它的长度，然后根据它的长度比较每个元素。

> ***最初*****l =[“ab”、“abc”、“bc”、“c”]**
> **当我们传递 key=len 作为参数时，它的工作方式类似于**
> **l =【2，3，2，1】**

## 蟒蛇 3

```
# Python code explaining min() and max()
def fun(element):
    return(len(element))

l =["ab", "abc", "bc", "c"]
print(max(l, key = fun))

# you can also write in this form
print(max(l, key = lambda element:len(element)))
```

**Output:** 

```
abc
abc
```

**另一个例子:**

## 蟒蛇 3

```
# Python code explaining min() and max()
l = [{'name':'ramu', 'score':90, 'age':24},
     {'name':'golu', 'score':70, 'age':19}]

# here anonymous function takes item as an argument.
print(max(l, key = lambda item:item.get('age')))
```

**Output:** 

```
{'age': 24, 'score': 90, 'name': 'ramu'}
```

类似的，我们可以根据需要使用 min()函数代替 max()函数。