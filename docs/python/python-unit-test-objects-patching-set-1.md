# Python |单元测试对象修补| Set-1

> 原文:[https://www . geesforgeks . org/python-unit-test-objects-patching-set-1/](https://www.geeksforgeeks.org/python-unit-test-objects-patching-set-1/)

问题在于编写单元测试，并且需要将补丁应用于选定的对象，以便断言它们在测试中是如何使用的(例如，断言使用某些参数被调用，访问选定的属性等)。).

为此，可以使用`**unittest.mock.patch()**`功能来帮助解决这个问题。这有点不寻常，但是`patch()`可以用作装饰器、上下文管理器或者独立的。

**Code #1: Using `unittest.mock.patch` as a decorator**

```
from unittest.mock import patch
import example
@patch('example.func')

def test1(x, mock_func):
    # Uses patched example.func
    example.func(x) 
    mock_func.assert_called_with(x)
```

**代码#2:用`unittest.mock.patch`做装饰**

```
with patch('example.func') as mock_func:
    example.func(x) 
    mock_func.assert_called_with(x)
```

**代码#3:使用 `unittest.mock.patch`手动修补东西。**

```
p = patch('example.func')
mock_func = p.start()
example.func(x)
mock_func.assert_called_with(x)
p.stop()
```

**代码#4:堆叠装饰器和上下文管理器来修补多个对象**

```
@patch('example.func1')
@patch('example.func2')
@patch('example.func3')

def test1(mock1, mock2, mock3):
    ...
def test2():
    with patch('example.patch1') as mock1, \
    patch('example.patch2') as mock2, \
    patch('example.patch3') as mock3:
    ...
```

`patch()`的工作原理是使用您提供的完全限定名获取一个现有对象，并用新值替换它。完成修饰函数或上下文管理器后，原始值将被恢复。默认情况下，值会被 MagicMock 实例替换。

**代码#5:示例**

```
x = 42
with patch('__main__.x'):
    print(x)

print (x)
```