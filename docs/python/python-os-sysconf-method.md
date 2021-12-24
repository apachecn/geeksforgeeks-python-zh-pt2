# Python | os.sysconf()方法

> 原文:[https://www.geeksforgeeks.org/python-os-sysconf-method/](https://www.geeksforgeeks.org/python-os-sysconf-method/)

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

***Python 中的 os.sysconf()*** 方法用于获取整数值系统配置值。它接受一个字符串参数*名称*，该参数指定要检索的配置值。

*名称*参数的所有可能值作为[***sysconf _ names***](https://www.geeksforgeeks.org/python-os-sysconf_names-object/)字典的关键字给出。我们还可以为那些没有包含在字典中的配置变量传递*名称*参数的整数值。

如果系统没有定义*名称*参数指定的配置变量，则 ***os.sysconf()*** 方法将返回 *None* ，如果名称没有指定任何现有的配置变量，则引发*值错误*异常。此外，如果主机操作系统不支持配置值，则会引发*错误*异常。

**注意:** ***os.sysconf()*** 方法仅在 UNIX 平台上可用。

> ***语法:*** os.sysconf(名称)
> ***参数:***
> **名称**:代表系统配置变量的字符串或整数值。
> ***返回类型:*** 该方法返回一个整数值，代表指定配置变量对应的配置值。

**代码:**使用 os.sysconf()方法

## 蟒蛇 3

```py
# Python program to explain os.sysconf() method

# importing os module 
import os

# System Configuration variable
name = "SC_PAGE_SIZE"

# Get the integer-valued 
# configuration value corresponding
# to the specified configuration 
# variable using os.sysconf() method
value = os.sysconf(name)

# Print the configuration value
print("% s :" % name, value) 

# System Configuration variable
name1 = "SC_INT_MIN"
name2 = "SC_INT_MAX"

# Get the integer-valued 
# configuration value corresponding
# to the specified configuration 
# variable using os.sysconf() method
value1 = os.sysconf(name1)
value2 = os.sysconf(name2)

# Print the configuration value
print("% s :" % name1, value1) 
print("% s :" % name2, value2) 

# We can also pass an integer 
# value for name parameter.
# integer value must be present in
# os.sysconf_names dictionary as value
# of any configuration variable
# for example
conf_var = "SC_INT_MIN"
name = os.sysconf_names[conf_var]
print("\nInteger value corresponding to % s:" % conf_var, name)

# Get the integer-valued 
# configuration value corresponding
# to the specified integer value 
# using os.sysconf() method
value = os.sysconf(name)

# Print the configuration value
print("Configuration value corresponding to % s :" % name, value)

# Note: -1 is returned if the
# configuration variable is not defined
# by the system 
```

**Output:** 

```py
SC_PAGE_SIZE : 4096
SC_INT_MIN : -2147483648
SC_INT_MAX : 2147483647

Integer value corresponding to SC_INT_MIN: 105
Configuration value corresponding to 105 : -2147483648
```

**代码#2:** 使用 os.sysconf()方法时可能出现的错误

## 蟒蛇 3

```py
# Python program to explain os.sysconf() method

# importing os module 
import os

# System Configuration variable
name = "PAGE_SIZE"

# If the specified name 
# is not a configuration variable
# then ValueError Exception 
# is raised

value = os.sysconf(name)
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
  File "sysconf.py", line 15, in 
    value = os.sysconf(name)
ValueError: unrecognized configuration name
```

**代码#3:** 使用 os.sysconf()方法时处理可能的错误

## 蟒蛇 3

```py
# Python program to explain os.sysconf() method

# importing os module 
import os

# System Configuration variable
name = "PAGE_SIZE"

# we can handle exception
# using try and except block

# Try getting the system 
# configuration value corresponding 
# to specified configuration variable
try :
    value = os.sysconf(name)
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
'PAGE_SIZE' is not a configuration variable
```