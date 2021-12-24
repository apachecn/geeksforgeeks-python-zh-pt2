# Python 程序从字符串计算算术运算

> 原文:[https://www . geesforgeks . org/python-程序到计算-算术-运算-从字符串/](https://www.geeksforgeeks.org/python-program-to-compute-arithmetic-operation-from-string/)

给定一个带有乘法元素的字符串，转换为这些乘法的总和。

> **输入** : test_str = '5×10，9×10，7×8'
> **输出** : 196
> **解释** : 50 + 90 + 56 = 196。
> 
> **输入** : test_str = '5×10，9×10'
> **输出** : 140
> **解释** : 50 + 90 = 140。

**方法 1:使用 map() + mul + sum() + split()**

上述功能的组合可以用来解决这个问题。在本例中，我们使用 [sum()](https://www.geeksforgeeks.org/sum-function-python/) 执行求和，使用 [mul()](https://www.geeksforgeeks.org/python-sympy-mul-method/#:~:text=Mul()%20method,-Last%20Updated%3A%2011&text=With%20the%20help%20of%20sympy,can%20form%20a%20mathematical%20expression.&text=Return%20%3A%20Return%20the%20product%20of%20two%20variables.) 、 [split()](https://www.geeksforgeeks.org/python-string-split/#:~:text=split()%20method%20returns%20a,string%20by%20the%20specified%20separator.&text=Parameters%20%3A,splits%20at%20this%20specified%20separator.) 执行乘法，用于分割元素以创建乘法操作数。[映射()](https://www.geeksforgeeks.org/python-map-function/)用于将乘法逻辑扩展到每次计算。

## 蟒蛇 3

```
# importing module
from operator import mul

# initializing string
test_str = '5x6, 9x10, 7x8'

# printing original string
print("The original string is : " + str(test_str))

# sum() is used to sum the product of each computation
res = sum(mul(*map(int, ele.split('x'))) for ele in test_str.split(', '))

# printing result
print("The computed summation of products : " + str(res))
```

**Output**

```
The original string is : 5x6, 9x10, 7x8
The computed summation of products : 176

```

**方法 2:使用 eval() + replace()**

在本例中，我们将乘法符号转换为乘法运算符(' ***** ')，同样，逗号符号转换为算术“ **+** ”符号。然后 [eval()](https://www.geeksforgeeks.org/eval-in-python/) 执行内部计算并返回结果。

## 蟒蛇 3

```
# initializing string
test_str = '5x6, 9x10, 7x8'

# printing original string
print("The original string is : " + str(test_str))

# using replace() to create eval friendly string
temp = test_str.replace(',', '+').replace('x', '*')

# using eval() to get the required result
res = eval(temp)

# printing result
print("The computed summation of products : " + str(res))
```

**Output**

```
The original string is : 5x6, 9x10, 7x8
The computed summation of products : 176

```