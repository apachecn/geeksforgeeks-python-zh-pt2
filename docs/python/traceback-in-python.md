# Python 中的回溯

> 原文:[https://www.geeksforgeeks.org/traceback-in-python/](https://www.geeksforgeeks.org/traceback-in-python/)

**Traceback** 是一个 python 模块，它提供了一个标准的接口来提取、格式化和打印 python 程序的堆栈痕迹。当它打印堆栈跟踪时，它完全模拟了 python 解释器的行为。当您想在任何一步打印堆栈跟踪时都很有用。它们通常在异常发生时出现。由于回溯提供了关于异常的所有信息，因此跟踪和修复异常变得更加容易。

**异常堆栈跟踪的一般结构:**

```
Traceback for most recent call
Location of the program 
Line in the program where error was encountered
Name of the error: relevant information about the exception 

```

**示例:**

```
Traceback (most recent call last):
  File "C:/Python27/hdg.py", line 5, in 
    value = A[5]
IndexError: list index out of range

```

该模块使用回溯对象，这是存储在`sys.last_traceback`变量中的对象类型，并作为第三项从`sys.exc_info()`返回。

## 模块中的功能

*   追溯。 **print_tb** (tb，limit = None，file = None):如果 limit 为正数，它将从回溯对象 tb 中打印最大限制堆栈跟踪条目。否则，打印最后一个 abs(限制)条目。如果省略“限制”或“无”，则打印所有条目。如果文件被省略或无，输出将转到 sys.stderr 否则，它应该是一个打开的文件或类似文件的对象来接收输出。
*   追溯。 **print_exception** (词根，值，tb，限制=无，文件=无，链=真) :从回溯对象 tb 到文件打印异常信息和堆栈跟踪条目。如果 tb 不是无，它将打印一个头追溯(最近一次调用的最后一次):。它在堆栈跟踪后打印异常的词根和值。如果类型(值)是 SyntaxError，并且值具有适当的格式，它将打印出现语法错误的行，并显示一个指示错误大致位置的插入符号。
*   追溯。 **print_exc** (limit = None，file = None，chain = True):这是 print_exc 异常(*sys.exc_info()，limit，file，chain)的简写。
*   追溯。 **print_last** (limit = None，file = None，chain = True):只有在异常到达交互提示后才起作用。这是 print_exception(sys.last_type，sys.last_value，sys.last_traceback，limit，file，chain)的简写。
*   追溯。 **print_stack** (f =无，limit =无，file =无) :如果 limit 为正数，则打印到 limit stack trace。否则，打印最后一个 abs(限制)条目。如果省略“限制”或“无”，将打印所有条目。可选的 f 参数可用于指定要开始的替代堆栈帧。
*   追溯。 **extract_tb** (tb，limit = None):返回一个 *StackSummary* 对象，表示从回溯对象 tb 中提取的“预处理”堆栈跟踪条目列表( *FrameSummary* 对象，包含属性 filename、lineno、name 和 line)。这对于堆栈跟踪的替代格式很有用。
*   追溯。 **extract_stack** (f =无，限制=无) :从当前堆栈帧中提取原始回溯。返回值的格式与 extract_tb()相同。
*   追溯。**format _ list**(extracted _ list):给定一个元组列表或 *FrameSummary* 对象，返回一个准备打印的字符串列表。结果列表中的每个字符串对应于参数列表中具有相同索引的项。每个字符串以换行符结尾；字符串也可能包含内部换行符。
*   追溯。 **format_exception_only** (词根，值) :格式化回溯的异常部分。参数是异常类型和值，如 sys.last_type 和 sys.last_value 给出的值。它返回一个字符串列表，每个字符串都以新的一行结束。
*   追溯。 **format_exception** (词根、值、tb、limit = None，chain = True):格式化堆栈跟踪和异常信息。这些参数的含义与 print_exception()的相应参数相同。它返回一个字符串列表，每个字符串以新的一行结束，有些字符串也有内部换行符。当这些行被连接并打印时，它们会生成与 print_exception()完全相同的输出。
*   追溯。 **format_exc** (limit = None，chain = True):这类似于 print_exc(limit)，只是它返回一个字符串，而不是打印到一个文件。
*   追溯。 **format_tb** (tb，limit = None):format _ list(extract _ TB(TB，limit))的简写。
*   追溯。 **format_stack** (f =无，limit =无):format_list(extract_stack(f，limit))的简写。
*   追溯。 **clear_frames** (tb):通过调用每个帧对象的 clear()方法，清除回溯 tb 中所有堆栈帧的局部变量。
*   追溯。**走栈** (f):从给定的帧走一个跟随 f.f_back 的栈，产生每个帧的帧和行号。如果 f 为无，则使用当前堆栈。此帮助器与 StackSummary.extract()一起使用。
*   追溯。 **walk_tb** (tb):在 tb_next 之后进行回溯，得出每一帧的帧号和行号。此帮助器与 StackSummary.extract()一起使用。

**示例:**打印异常堆栈跟踪的程序。

```
# importing module
import traceback

# declaring array
A = [1, 2, 3, 4]

try:
    value = A[5]

except:
    # printing stack trace
    traceback.print_exc()

# out of try-except
# this statement is to show that the program continues 
# normally after the exception is handled
print("end of program")
```

**输出:**

```
Traceback (most recent call last):
  File "C:/Python27/van.py", line 8, in 
    value = A[5]
IndexError: list index out of range
end of program
>>> 

```

## 模块中的类

**tracebackeepexception 类:** `TracebackException`对象是从实际异常中创建的，用于捕获数据以供以后打印。

> 班级回溯。回溯异常(exc_type，exc_value，exc_traceback，* limit = None，lookup_lines = True，capture_locals = False)

类`TracebackException`包含以下对象:

*   **_ _ 起因 __** :原`__cause__`的一个`TracebackException`。
*   **_ _ 上下文 __** :原`__context__`的一个`TracebackException`。
*   **__suppress_context__** :原始异常的`__suppress_context__` 值。
*   **栈**:一个`StackSummary` 代表回溯
*   **exc_type** :原回溯的类。
*   **文件名**:对于语法错误–发生错误的文件名。
*   **行号**:对于语法错误–发生错误的行号。
*   **文本**:对于语法错误–发生错误的文本。
*   **偏移量**:对于语法错误–发生错误的文本中的偏移量。
*   **消息**:对于语法错误–编译器错误消息。
*   **class method from _ exc(exc，* limit = None，lookup_lines = True，capture_locals = False)** :捕获一个异常，用于以后的渲染。
*   **格式(*，链=真)**:格式化异常。如果链不为真，`__cause__` 和`__context__` 将不被格式化。它返回以换行符结尾的字符串，很少有内部换行符。指示发生了哪个异常的消息总是输出中的最后一个字符串。
*   **format_exception_only()** :格式化回溯的异常部分。它还返回以换行符结尾的字符串。正常情况下，发电机发出一根弦；但是，对于`SyntaxError` 异常，它会发出几行(打印时)显示语法错误发生位置的详细信息。指示发生了哪个异常的消息总是输出中的最后一个字符串。

**示例:**

```
# importing the modules
import traceback
import sys

a=3
b=0
try:
    a/b
except Exception as e:
    exc_type, exc_value, exc_tb = sys.exc_info()
    tb = traceback.TracebackException(exc_type, exc_value, exc_tb)
    print(''.join(tb.format_exception_only()))
```

**输出:**

```
ZeroDivisonError: division by zero
```

**堆栈摘要类:**这个类的对象代表一个准备格式化的调用堆栈。

```
class traceback.StackSummary
```

*   **class method extract(frame _ gen，* limit = None，lookup_lines = True，capture_locals = False)** :从帧生成器构造一个 StackSummary 对象。如果提供了限制，则只拍摄这么多帧。如果 lookup_lines 为 False，则返回的 FrameSummary 对象还没有读入它们的行，这使得创建 StackSummary 的成本更低。如果 capture_locals 为 True，则每个框架摘要中的局部变量将被捕获为对象表示。
*   **class method from _ list(a _ list)**:从提供的框架摘要对象列表或旧式元组列表中构造 StackSummary 对象。
*   **format()** :返回准备打印的字符串列表。结果列表中的每个字符串对应于堆栈中的单个帧。每个字符串以换行符结尾；字符串也可能包含内部换行符。对于同一帧和同一行的长序列，显示前几个重复，后面是一个摘要行，说明进一步重复的确切次数。然而，在较新的版本中，重复帧的长序列被缩写。

**示例:**

```
# importing the modules
import traceback
import sys

def call1(f):

  # inside call1()
  # call1() calling call2()
  call2(f)

def call2(f):
  # inside call2()
  # calling f()
  f()

def f():

    # inside f()
    summary = traceback.StackSummary.extract(
        traceback.walk_stack(None)
    )
    print(''.join(summary.format()))

# calling f() using call1()
call1(f)
```

**输出:**

```
File "main.py", line 19, in f
    summary = traceback.StackSummary.extract(
  File "main.py", line 14, in call2
    f()
  File "main.py", line 9, in call1
    call2(f)
  File "main.py", line 25, in 
    call1(f)
```

**框架概要类:**
`FrameSummary` 对象表示回溯中的单个框架。

```
class traceback.FrameSummary(filename, lineno, name, lookup_line = True, locals = None, line = None)
```

它表示正在格式化或打印的回溯或堆栈中的单个帧。它可以选择在其中包含框架的字符串版本。如果 lookup_line 为 False，则在访问 FrameSummary 的 line 属性之前，不会查找源代码。可以直接提供该行，这将完全阻止行查找的发生。局部变量是一个可选的局部变量字典，如果提供了，变量表示将存储在摘要中以供以后显示。

**示例:**

```
# importing the modules
import traceback
import sys

def call1(f):

    # inside call1()
    # call1() calling call2()
    call2(f)

def call2(f):
    # inside call2()
    # calling f()
    f()

template = (
    '{frame.filename}:{frame.lineno}:{frame.name}:\n'
    '    {frame.line}'
)

def f():
    summary = traceback.StackSummary.extract(
        traceback.walk_stack(None)
    )
    for frame in summary:
        print(template.format(frame=frame))

# calling f() through call1()
call1(f)
```

**输出:**

```
main.py:21:f:
    summary = traceback.StackSummary.extract(
main.py:13:call2:
    f()
main.py:8:call1:
    call2(f)
main.py:28::
    call1(f)
```

参考-

*   https://docs.python.org/3/library/traceback.html#traceback.extract_tb
*   https://pymotw.com/3/traceback/