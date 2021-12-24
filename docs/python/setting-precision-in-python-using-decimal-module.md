# 使用十进制模块在 Python 中设置精度

> 原文:[https://www . geeksforgeeks . org/setting-precision-in-python-use-decimal-module/](https://www.geeksforgeeks.org/setting-precision-in-python-using-decimal-module/)

Python 中的十进制模块可以用来设置一个数字的精确值。十进制模块的默认值最多为 28 个有效数字。但是，可以使用 *getcontext()进行更改。prec* 法。

下面的程序演示了*小数*模块的使用，通过计算 2 个数字的平方根达到默认的位数。

## python 3

```py
# Import required modules
import decimal  

# Create decimal object
ob1 = decimal.Decimal(5).sqrt()  
ob2 = decimal.Decimal(7).sqrt()

# Display value  
print(ob1)
print(ob2)
```

**输出**

```py
2.236067977499789696409173669
2.645751311064590590501615754

```

我们可以将精度设置为 n 个有效数字。*小数。prec* 必须在全局范围内声明，以便所有十进制对象可以有 n 个有效数字。

T5】蟒 3T7

```py
# Import required module
import decimal

# Set precision to a fixed value 
decimal.getcontext().prec = 6  

# Create Decimal object
ob1 = decimal.Decimal(5).sqrt()  
ob2 = decimal.Decimal(7).sqrt()

# Display value up to 6 significant figures
print(ob1)
print(ob2)
```

T8T10**输出**T1