# Python 通过声明

> 原文:[https://www.geeksforgeeks.org/python-pass-statement/](https://www.geeksforgeeks.org/python-pass-statement/)

**pass** 语句为空语句。但是 pass 和 comment 的区别在于注释被解释器忽略，而 pass 没有被忽略。

**pass** 语句一般用作占位符，即当用户不知道写什么代码时。因此用户只需将**通行证**放在该行。有时，当用户不想执行任何代码时，会使用 **pass** 。因此，用户可以简单地将**放在不允许空代码的地方，比如循环、函数定义、类定义或 if 语句中。所以使用 pass 语句用户可以避免这个错误。**

**语法:**

```py
pass
```

**例 1:** Pass 语句可用于空函数

## 蟒蛇 3

```py
def geekFunction:
  pass
```

**例 2:** pass 语句也可以用于空类

## 蟒蛇 3

```py
class geekClass:
  pass
```

**示例 3:** 当用户不知道在循环中编码什么时，可以在 for 循环中使用 pass 语句

## 蟒蛇 3

```py
n = 10
for i in range(n):

  # pass can be used as placeholder
  # when code is to added later
  pass
```

**示例 4:** pass 语句可以与条件语句一起使用

## 蟒蛇 3

```py
a = 10
b = 20

if(a<b):
  pass
else:
  print("b<a")
```

**示例 5:** 我们再举一个例子，当条件为真时，pass 语句被执行

## 蟒蛇 3

```py
li =['a', 'b', 'c', 'd']

for i in li:
    if(i =='a'):
        pass
    else:
        print(i)
```

**输出:**

```py
b
c
d
```