# Python | locals()函数

> 原文:[https://www.geeksforgeeks.org/python-locals-function/](https://www.geeksforgeeks.org/python-locals-function/)

**Python locals()函数**返回当前局部符号表的字典。

*   **符号表:**是由编译器创建的数据结构，用于存储执行程序所需的所有信息。
*   **本地符号表:**该符号表存储程序本地范围所需的所有信息，该信息使用 python 内置函数 locals()进行访问。

> **语法:**局部变量()
> 
> **参数:**该函数不接受任何输入参数。
> 
> **返回类型:**返回本地符号表中存储的信息。

## Python 局部变量()方法示例

### **示例 1:** Python 局部变量()在局部范围内工作

## 蟒蛇 3

```
# Python program to understand about locals
# here no local variable is present

def demo1():
    print("Here no local variable  is present : ", locals())

# here local variables are present
def demo2():
    name = "Ankit"
    print("Here local variables are present : ", locals())

# driver code
demo1()
demo2()
```

**输出；**

```
Here no local variable  is present :  {}
Here local variables are present :  {'name': 'Ankit'}
```

### **示例 2:** 使用局部变量更新()

与 [globals()](https://www.geeksforgeeks.org/python-globals-function/) 不同，该函数不能修改局部符号表的数据。下面的程序解释得很清楚。

## 蟒蛇 3

```
# Python program to understand about locals
# here no local variable is present

def demo1():
    print("Here no local variable  is present : ", locals())

# here local variables are present
def demo2():
    name = "Ankit"
    print("Here local variables are present : ", locals())
    print("Before updating name is  : ", name)

    # trying to change name value
    locals()['name'] = "Sri Ram"

    print("after updating name is : ", name)

# driver code
demo1()
demo2()
```

**输出:**

```
Here no local variable  is present :  {}
Here local variables are present :  {'name': 'Ankit'}
Before updating name is  :  Ankit
after updating name is :  Ankit
```

### **示例 3:** 局部变量()用于全球环境

在全局环境中，局部符号表与全局符号表相同。

## 蟒蛇 3

```
# Python program to understand about locals

# data using locals
print("This is using locals() : ", locals())

# data using globals
print("This is using globals() : ", globals())
```

**输出:**

> 这是使用局部变量():{'__name__': '__main__ '，' __doc__ ':'为 IPython 交互环境自动创建的模块'，' __package__ ':无，' __loader__ ':无，' __spec__ ':无，__ 内建 __': <module>，' __ 内建 __': <module>，' _ ih:["，'从 bs4 导入美化队列导入队列导入多处理\n 队列导入队列，空\n 从并发期货导入线程池导入。格式(urlparse(self.seed_url))。scheme，\n urlparse(self.seed_url)。netloc)\ n self . pool = ThreadPoolExecutor(max _ workers = 5)\ n self . scratched _ pages = set([])\ n self . crawl _ queu = Queue()\ n self . crawl _ queu</module></module>

## Python 局部变量 VS 全局函数

python 中的 python globals()函数返回当前全局符号表的字典。

```
Syntax: globals()

Parameters: No parameters required.
```

## 蟒蛇 3

```
# Python3 program to demonstrate global() function

# global variable
a = 5

def func():
    c = 10
    d = c + a

    # Calling globals()
    globals()['a'] = d
    print (d)

# Driver Code   
func()
```

**输出:**

```
15
```

Python 中的 Python locals()函数返回当前本地符号表的字典。

## 蟒蛇 3

```
locals()
```

**输出:**

> {“_ _ name _ _”:“_ _ main _ _”，
> 
> __doc__ ':“为 IPython 交互环境自动创建的模块”，
> 
> __ 包 _ _ ':无，
> 
> __loader__ ':无，
> 
> __ 规格 _ _ ':无，
> 
> __ 内置 __': <module>，</module>
> 
> “_ _ builtin _ _”:t0[
> 
> _ih': ["，
> 
> #演示使用\n# len()方法的 Python 程序\n\n#下面字符串的长度为 5\nstring = "极客" \nprint(len(string))\n\n#下面字符串的长度为 15\nstring = "极客的极客" \nprint(len(string))'，
> 
> # Python 程序演示使用\n# len()方法\n\n# L