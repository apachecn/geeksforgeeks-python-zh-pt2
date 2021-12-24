# Python |单元测试对象修补| Set-2

> 原文:[https://www . geesforgeks . org/python-unit-test-objects-patching-set-2/](https://www.geeksforgeeks.org/python-unit-test-objects-patching-set-2/)

通常用作替换值的 MagicMock 实例旨在模拟可调用和实例。它们记录关于使用的信息，并允许进行断言，如下面给出的代码所示–

**Code #6:**

```

from unittest.mock  
import MagicMock 
m = MagicMock(return_value = 10) 
print(m(1, 2, debug = True), "\n")  

m.assert_called_with(1, 2, debug = True)
m.assert_called_with(1, 2)  
```

**输出:**

```

10  
Traceback (most recent call last):    
   File "", line 1, in     
   File ".../unittest/mock.py", line 726, in assert_called_with      
      raise AssertionError(msg) 
AssertionError: Expected call: mock(1, 2) 
Actual call: mock(1, 2, debug=True)

```

**代码#7:通过将值作为第二个参数提供给`patch()`** 来替换该值

```
print("x : ", x)

with patch('__main__.x', 'patched_value'):
    print(x)
patched_value

print("x : ", x)
```

**输出:**

```
x : 42
x : 42
```

通常用作替换值的 MagicMock 实例旨在模拟可调用和实例。它们记录关于使用的信息，并可以做出断言。

```
from unittest.mock import MagicMock
m = MagicMock(return_value = 10)
print(m(1, 2, debug = True), "\n")

m.assert_called_with(1, 2, debug = True)
m.assert_called_with(1, 2)
```

**输出:**

```
10

Traceback (most recent call last):
    File "", line 1, in 
    File ".../unittest/mock.py", line 726, in assert_called_with
       raise AssertionError(msg)
AssertionError: Expected call: mock(1, 2)
Actual call: mock(1, 2, debug=True)

```

**代码#8:处理示例**

```
m.upper.return_value = 'HELLO'
print (m.upper('hello'))

assert m.upper.called
m.split.return_value = ['hello', 'world']
print (m.split('hello world'))

m.split.assert_called_with('hello world')
print (m['blah'])

print (m.__getitem__.called)
```

**输出:**

```
'HELLO'
['hello', 'world']
<MagicMock name='mock.__getitem__()' id='4314412048'>
True
```

通常，这些类型的操作在单元测试中执行。用下面给出的代码中的一个函数的例子来解释

**代码#9 :**

```
from urllib.request import urlopen
import csv

def dowprices():
    u = urlopen('http://finance.yahoo.com/d/quotes.csv?s =@^DJI&f = sl1')
    lines = (line.decode('utf-8') for line in u)
    rows = (row for row in csv.reader(lines) if len(row) == 2)
    prices = { name:float(price) for name, price in rows }
    return prices
```

通常，这个函数使用`urlopen()` 从网络上获取数据并解析它。为了对其进行单元测试，可以使用更可预测的数据集。