# Python–饼图语法(@)

> 原文:[https://www.geeksforgeeks.org/python-pie-syntax/](https://www.geeksforgeeks.org/python-pie-syntax/)

一个[装饰器](https://www.geeksforgeeks.org/decorators-in-python/)，是一个可调用的，用来扩展其他可调用的功能。简单来说，它允许你用另一个功能来“装饰”一个功能。在本文中，“@”符号有时被装饰者称为“饼图语法”。pie 语法使得访问和扩展更加容易。

因为，我们已经用 staticmethod()和 classmethod()进行了装饰。因此，函数定义可能被一个或多个装饰表达式包装。当函数在包含函数定义的范围内被定义时，Decorator 表达式被求值。结果必须是可调用的，它是以函数对象作为唯一参数调用的。返回值绑定到函数名，而不是函数对象。多个装饰器可以嵌套方式应用。

**语法:**

```py
(Pie_syntax) <decorator_name>
any_callable

```

**示例:**

> @gfg
> 
> def 极客():
> 
> 。
> 
> 。

如果重复的赋值和调用语句看起来没有用，那么饼图语法就是救星。我们可以只在@符号后命名装饰函数，并将其放在要装饰的函数之前。

以下程序将帮助您更好地理解这一点:

**程序 1:**

## 蟒蛇 3

```py
# defining the decorator
def decor(func):
    print("#----------------#")
    func()
    print("#----------------#")

# using the decorator
@decor
def main():
    print("$ GeeksforGeeks {content}quot;)

if __name__ == 'main':
    main()
```

**输出:**

> #—————-#
> 
> $极客 forGeeks $
> 
> #—————-#

#### 链接饼图语法

我们也可以在一个功能中有多个装饰者，不一定只有一个**。**但是，记住装饰者的顺序很重要。装饰者被调用的顺序将直接影响输出。

**程序 2:**

## 蟒蛇 3

```py
# defining the 1st decorator
def decor1(func):
    print("_________________")

# defining the 2nd decorator
def decor2(func):
    print("$****************{content}quot;)
    func()
    print("$****************{content}quot;)

# using the decorator
@decor1
@decor2
def main():
    print("$ GeeksforGeeks  {content}quot;)

# Driver program to test the code
if __name__ == 'main':
    main()
```

**输出:**

> $****************$
> 
> $极客 forGeeks $
> 
> $****************$
> 
> _________________