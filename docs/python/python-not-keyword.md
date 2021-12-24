# Python 非关键字

> 原文:[https://www.geeksforgeeks.org/python-not-keyword/](https://www.geeksforgeeks.org/python-not-keyword/)

**Python not 关键字**是一个逻辑运算符，通常用于计算操作数的否定或相反布尔值。关键字*‘非’*是一元类型运算符，这意味着它只接受一个操作数进行逻辑运算，并返回操作数布尔值的补码。例如，如果我们将 false 作为 not 关键字的操作数，则返回值为 true。

> **语法:**不是 var

## **实际应用**

not 关键字可能的实际应用有:

*   该关键字主要用于更改[布尔值](https://www.geeksforgeeks.org/boolean-data-type-in-python/)。
*   与 [if 语句](https://www.geeksforgeeks.org/python-if-else/)连用。在 if 语句中，它用于否定条件
*   “not”关键字在关键字中也与[连用。当我们在数据集合中搜索特定值时，它与 in 关键字一起使用。](https://www.geeksforgeeks.org/python-in-keyword/)

**例 1:** 非真变量运算符的基本示例。

## 蟒蛇 3

```
# variable
a = True
print(not a)
```

**输出:**

```
False
```

**例 2:** 带变量的 not 运算符的基本示例。

## 蟒蛇 3

```
# variable
a = False
print(not a)
```

**输出:**

```
True
```

**例 3:** 特定条件下的例。

因为“not”关键字的基本属性是它用于反转操作数的真值。所以我们在这里可以看到，每一个值的结果都是从它们的真实值反过来的。在#5，我们可以看到比较操作结果将是假的，所以否定它，我们得到真值。明喻，我们可以看到所有的结果都是颠倒的。

## 蟒蛇 3

```
# Python code to demonstrait
# 'not' keyword

# Function showing working of not keyword
def geek_Func():

    # 1 Not with False boolean value
    geek_x = not False
    print('Negation  of False : ', geek_x)

    # 2 Not with true boolean value
    geek_y = not True
    print('Negation of True : ', geek_y)

    # 3 Not with result of and operation
    geek_and = not(True and False)
    print('Negation of result of And operation : ', geek_and)

    # 4 Not with result of or operation
    geek_or = not(True or False)
    print('Negation of result of or operation : ', geek_or)

    # 5 Not with result of compare operation
    geek_Com = not (5 > 7)
    print('Negation of result of And operation : ', geek_Com)

geek_Func()
```

**输出:**

```
Negation  of False :  True
Negation of True :  False
Negation of result of And operation :  True
Negation of result of or operation :  False
Negation of result of And operation :  True
```

**示例 4:** 在本代码中，我们用一个不同于布尔值的值展示了‘not’运算符的工作原理，并看看它是如何工作的。

## 蟒蛇 3

```
# Python code to demonstrait
# 'not' keyword

# Function showing working of not keyword
def geek_Func():

    # Not with String boolean value
    geek_Str = "geek"
    print('Negation  of String : ', not geek_Str)

    # Not with list boolean value
    geek_List = [1, 2, 3, 4]
    print('Negation of list : ', not geek_List)

    # Not with dictionary
    geek_Dict = {"geek": "sam", "collage": "Mit"}
    print('Negation of dictionary : ', not geek_Dict)

    # Not with Empty String
    geek_EDict = ""
    print('Negation of Empty String : ', not geek_EDict)

    # Not with Empty list
    geek_EList = []
    print('Negation of Empty List : ', not geek_EList)

    # Not with Empty dictionary
    geek_EStr = {}
    print('Negation of Empty Dictionary : ', not geek_EStr)

geek_Func()
```

**输出:**

```
Negation  of String :  False
Negation of list :  False
Negation of dictionary :  False
Negation of Empty String :  True
Negation of Empty List :  True
Negation of Empty Dictionary :  True
```

在上面的例子中，我们看到用 not 关键字将所有数据类型视为操作数。“not”对所有有值的数据类型都为 true，对空值的数据类型为 false。

**示例 5:** 列表示例

## 蟒蛇 3

```
# Python code to demonstrait
# 'not' keyword

geek_list = [5, 10, 20, 59, 134, 83, 95]

# Function showing working of not keyword
def geek_Func():

    # Using not with if statement
    if not geek_list:
        print("Inputed list is Empty")
    else:
        for i in geek_list:
            if not(i % 5):

                # Using not with in statement
                if i not in (0, 10):
                    print("Multiple is not in range")
                else:
                    print(i)
            else:
                print("The number is not multiple of 5")

geek_Func()
```

**输出:**

```
Multiple is not in range
10
MUltiple is not in range
The number is not multiple of 5
The number is not multiple of 5
The number is not multiple of 5
Multiple is not in range
```