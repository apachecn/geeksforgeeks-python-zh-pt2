# 使用 doctest 模块进行 Python 测试

> 原文:[https://www . geesforgeks . org/testing-in-python-use-doctest-module/](https://www.geeksforgeeks.org/testing-in-python-using-doctest-module/)

**Python 中的 Docstrings** 不仅用于描述一个类或一个函数，以更好地理解代码和使用，还用于测试目的。

**文档测试模块**在文档字符串中找到看起来像交互式外壳命令的模式。

输入和预期输出包含在 docstring 中，然后 doctest 模块使用这个 docstring 来测试处理后的输出。
通过文档字符串解析后，解析的文本作为 python shell 命令执行，并将结果与从文档字符串中提取的预期结果进行比较。

这里有一个简单的例子:

> 1.从 doctest 导入 testmod 来测试该函数。
> 2。定义我们的测试功能。
> 3。提供一个合适的文档字符串，其中包含某些输入的期望输出。
> 4。定义逻辑。
> 5。使用要测试的函数的名称调用 testmod 函数，并将详细的 True 设置为参数。
> 
> **注意:**所有参数都是可选的。函数的名称被显式传递给 testmod。如果有多种功能就很有用。

**实施**

```
# import testmod for testing our function
from doctest import testmod

# define a function to test
def factorial(n):
    '''
    This function calculates recursively and
    returns the factorial of a positive number.
    Define input and expected output:
    >>> factorial(3)
    6
    >>> factorial(5)
    120
    '''
    if n <= 1:
        return 1
    return n * factorial(n - 1)

# call the testmod function
if __name__ == '__main__':
    testmod(name ='factorial', verbose = True)
```

**输出:**

```
Trying:
    factorial(3)
Expecting:
    6
ok
Trying:
    factorial(5)
Expecting:
    120
ok
1 items had no tests:
    factorial
1 items passed all tests:
   2 tests in factorial.factorial
2 tests in 2 items.
2 passed and 0 failed.
Test passed.

```

现在，测试失败。如果我们的逻辑错了呢？

```
# import testmod for testing our function
from doctest import testmod

# define a function to test
def factorial(n):
    '''
    This function calculates recursively and
    returns the factorial of a positive number.
    Define input and expected output:
    >>> factorial(3)
    6
    >>> factorial(5)
    120
    '''
    if n <= 1:
        return 1
    # wrong logic for factorial
    return factorial(n - 1)

# call the testmod function
if __name__ == '__main__':
    testmod(name ='factorial', verbose = True)
```

**输出:**

```
Trying:
    factorial(3)
Expecting:
    6
**********************************************************************
File "woking_with_csv.py", line 33, in factorial.factorial
Failed example:
    factorial(3)
Expected:
    6
Got:
    1
Trying:
    factorial(5)
Expecting:
    120
**********************************************************************
File "woking_with_csv.py", line 35, in factorial.factorial
Failed example:
    factorial(5)
Expected:
    120
Got:
    1
1 items had no tests:
    factorial
**********************************************************************
1 items had failures:
   2 of   2 in factorial.factorial
2 tests in 2 items.
0 passed and 2 failed.
***Test Failed*** 2 failures.

```

**注意**:如果‘verbose’设置为 False(默认)，则只在失败的情况下显示输出，而不是在成功的情况下。