# Python | os.confstr()方法

> 原文:[https://www.geeksforgeeks.org/python-os-confstr-method/](https://www.geeksforgeeks.org/python-os-confstr-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

***Python 中的 os.confstr()*** 方法用于获取字符串值的系统配置值。它通常接受字符串参数*名称*，该参数指定要检索的配置值。

*名称*参数的所有可能值作为[***confstr _ name***](https://www.geeksforgeeks.org/python-os-confstr_names-object/)字典的关键字给出。我们还可以为那些没有包含在字典中的配置变量传递*名称*参数的整数值。

如果系统没有定义*名称*参数指定的配置变量，则 ***os.confstr()*** 方法将返回 *None* ，如果名称没有指定任何现有的配置变量，则引发*值错误*异常。此外，如果主机操作系统不支持配置值，则会引发*错误*异常。

**注意:** ***os.confstr()*** 方法仅在 UNIX 平台上可用。

> ***语法:*** os.confstr(名称)
> ***参数:***
> **名称**:代表系统配置变量的字符串或整数值。
> ***返回类型:*** 该方法返回一个字符串值，代表指定配置变量对应的配置值。

**代码:**使用 os.confstr()方法

## 蟒蛇 3

```py
# Python program to explain os.confstr() method

# importing os module 
import os

# System Configuration variable
name = "CS_GNU_LIBC_VERSION"

# Get the configuration value
# corresponding to the
# specified configuration 
# variable using os.confstr() method
value = os.confstr(name)

# Print the configuration value
print("% s :" % name, value) 

# System Configuration variable
name = "CS_PATH"

# Get the configuration value
# corresponding to the 
# specified configuration 
# variable using os.confstr() method
value = os.confstr(name)

# Print the configuration value
print("% s :" % name, value)

# We can also pass an integer 
# value for name parameter.
# for example
conf_var = "CS_GNU_LIBC_VERSION"
name = os.confstr_names[conf_var]
print("\nInteger value corresponding to % s:" % conf_var, name)

# Get the configuration value
# corresponding to the 
# specified integer value 
# using os.confstr() method
value = os.confstr(name)

# Print the configuration value
print("Configuration value corresponding to % s :" % name, value)

# Note: -1 is returned if the
# configuration variable is not defined
# by the system 
```

**Output:** 

```py
CS_GNU_LIBC_VERSION : glibc 2.26
CS_PATH : /bin:/usr/bin

Integer value corresponding to CS_GNU_LIBC_VERSION: 2
Configuration value corresponding to 2 : glibc 2.26
```

**代码#2:** 使用 os.confstr()方法时可能出现的错误

## 蟒蛇 3

```py
# Python program to explain os.confstr() method

# importing os module 
import os

# System Configuration variable
name = "cs_PATH"

# If the specified name 
# is not a configuration variable
# then ValueError Exception 
# is raised

value = os.confstr(name)
print("% s:" % name, value)

# Similarly, if the a specific
# value for name parameter is
# not supported by host operating system
# then OSError exception
# is raised.
```

**Output:** 

```py
Traceback (most recent call last):
  File "confstr.py", line 15, in 
    value = os.confstr(name)
ValueError: unrecognized configuration name
```

**代码#3:** 使用 os.confstr()方法时处理可能的错误

## 蟒蛇 3

```py
# Python program to explain os.confstr() method

# importing os module 
import os

# System Configuration variable
name = "cs_PATH"

# we can handle exception
# using try and except block

# Try getting the system 
# configuration value corresponding 
# to specified configuration variable
try :
    value = os.confstr(name)
    print("% s:" % name, value)

# If the specified name is
# not a configuration variable
except ValueError :
    print("'% s' is not a configuration variable" % name)

# If the specified name is
# not supported by the 
# operating system 
except OSError :
    print("'% s' is not supported by Operating system" % name) 
```

**Output:** 

```py
'cs_PATH' is not a configuration variable
```