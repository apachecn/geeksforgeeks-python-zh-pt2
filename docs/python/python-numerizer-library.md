# Python 记数器库

> 原文:[https://www.geeksforgeeks.org/python-numerizer-library/](https://www.geeksforgeeks.org/python-numerizer-library/)

**记数器**是根据**国际数字系统**转换英文数字的图书馆。它可以转换由一个周期、千周期、百万周期和万亿周期组成的输入。每个周期由三位数字组成，即 1 位、10 位和 100 位。它是一个广泛使用的自然语言处理和数据科学库。

**注:**转换**印度数字系统**的数字，首先要写在**国际数字系统**中。

**安装库:**

```
pip install numerizer 
```

**例 1:**

## 蟒蛇 3

```
# Importing Numerize function
# From Numerizer Library
from numerizer import numerize

# We can get integer value
# in output by converting explicitly
a = int(numerize('Three'))
print(a)
print(numerize('five thousand two hundred and twenty'))

# If we are not converting our
# output explicitly into integer
# then by default it will return
# a string value
a = numerize('forty four thousand four hundred forty four')
print(a)
print("Type", type(a))

a = numerize('sixty billion forty million twenty thousand four hundred six')
print(a)
```

**输出:**

```
3
5220
44444
Type 
60040020406
```

**例 2:**

## 蟒蛇 3

```
# Importing Numerize function
# From Numerizer Library
from numerizer import numerize

# here we can also pass numerical
# values with corresponding periods
# it will still give same output
a = numerize('320 thousand three hundred twenty ')
print(a)

a = numerize('990 trillion 988 billion 881 million 999 thousand nine hundred ninety nine')
print(a)

# here we can also get float values
# in our output by using "half" and
# "quarter" terms in input
a = numerize('twenty nine one half')
print(a)
type(a)

# here we are explicitly converting
# our output into float type
a = float(numerize(' nine hundred ninety and two half'))

# it will add two half
# (i.e. 1/2+1/2) to our no
# which will add 1 to our answer
print(a)
type(a)

a = numerize('two thousand four hundred twenty and three quarters')

# it will add (3/4) to our answer
print(a)
```

**输出:**

```
320320 
990988881999999
29.5
991.0
2420.75
```

**注意:**numericize 总是将字符串作为输入，否则会引发语法错误。