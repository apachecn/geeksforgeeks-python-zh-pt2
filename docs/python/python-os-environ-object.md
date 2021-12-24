# Python | os .约对象

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-OS-约对象/

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。

Python 中的`***os.environ***`是一个表示用户环境变量的映射对象。它返回一个以用户的环境变量为关键字，以它们的值为值的字典。

`***os.environ***`的行为类似于 python 字典，因此可以执行所有常见的字典操作，如 get 和 set。我们也可以修改`***os.environ***`，但是任何更改都将只对分配它的当前流程有效，并且不会永久更改该值。

> ***语法:*** os .约
> 
> ***参数:*** 是不可调用对象。因此，不需要任何参数
> 
> ***返回类型:*** 返回表示用户环境变量的字典

**代码#1:** 使用 os.environ 获取对环境变量的访问

```
# Python program to explain os.environ object 

# importing os module 
import os
import pprint

# Get the list of user's
# environment variables
env_var = os.environ

# Print the list of user's
# environment variables
print("User's Environment variable:")
pprint.pprint(dict(env_var), width = 1)
```

**Output:**

```
{'CLUTTER_IM_MODULE': 'xim',
 'COLORTERM': 'truecolor',
 'DBUS_SESSION_BUS_ADDRESS': 'unix:path=/run/user/1000/bus',
 'DESKTOP_SESSION': 'ubuntu',
 'DISPLAY': ':0',
 'GDMSESSION': 'ubuntu',
 'GJS_DEBUG_OUTPUT': 'stderr',
 'GJS_DEBUG_TOPICS': 'JS '
                     'ERROR;JS '
                     'LOG',
 'GNOME_DESKTOP_SESSION_ID': 'this-is-deprecated',
 'GNOME_SHELL_SESSION_MODE': 'ubuntu',
 'GTK_IM_MODULE': 'ibus',
 'HOME': '/home/ihritik',
 'IM_CONFIG_PHASE': '2',
 'JAVA_HOME': '/opt/jdk-10.0.1',
 'JOURNAL_STREAM': '9:28586',
 'JRE_HOME': '/opt/jdk-10.0.1/jre',
 'LANG': 'en_IN',
 'LANGUAGE': 'en_IN:en',
 'LESSCLOSE': '/usr/bin/lesspipe '
              '%s '
              '%s',
 'LESSOPEN': '| '
             '/usr/bin/lesspipe '
             '%s',
 'LOGNAME': 'ihritik',
 'PATH': '/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:
/usr/local/games:/snap/bin:/usr/local/java/jdk-10.0.1/bin:
/usr/local/java/jdk-10.0.1/jre/bin:/opt/jdk-10.0.1/bin:/opt/jdk-10.0.1/jre/bin',
 'PWD': '/home/ihritik',
 'QT4_IM_MODULE': 'xim',
 'QT_IM_MODULE': 'ibus',
 'SESSION_MANAGER': 'local/hritik:@/tmp/.ICE-unix/1127, unix/hritik:/tmp/.ICE-unix/1127',
 'SHELL': '/bin/bash',
 'SHLVL': '2',
 'SSH_AUTH_SOCK': '/run/user/1000/keyring/ssh',
 'TERM': 'xterm-256color',
 'TEXTDOMAIN': 'im-config',
 'TEXTDOMAINDIR': '/usr/share/locale/',
 'USER': 'ihritik',
 'USERNAME': 'ihritik',
 'VTE_VERSION': '4804',
 'WAYLAND_DISPLAY': 'wayland-0',
 'XDG_CONFIG_DIRS': '/etc/xdg/xdg-ubuntu:/etc/xdg',
 'XDG_CURRENT_DESKTOP': 'ubuntu:GNOME',
 'XDG_MENU_PREFIX': 'gnome-',
 'XDG_RUNTIME_DIR': '/run/user/1000',
 'XDG_SEAT': 'seat0',
 'XDG_SESSION_DESKTOP': 'ubuntu',
 'XDG_SESSION_ID': '2',
 'XDG_SESSION_TYPE': 'wayland',
 'XDG_VTNR': '2',
 'XMODIFIERS': '@im=ibus',
 '_': '/usr/bin/python3'}

```

**代码#2:** 访问特定的环境变量

```
# Python program to explain os.environ object 

# importing os module 
import os

# Get the value of
# 'HOME' environment variable
home = os.environ['HOME']

# Print the value of
# 'HOME' environment variable
print("HOME:", home)

# Get the value of
# 'JAVA_HOME' environment variable
# using get operation of dictionary
java_home = os.environ.get('JAVA_HOME')

# Print the value of
# 'JAVA_HOME' environment variable
print("JAVA_HOME:", java_home)
```

**Output:**

```
HOME: /home/ihritik
JAVA_HOME: /opt/jdk-10.0.1

```

**代码#3:** 修改环境变量

```
# Python program to explain os.environ object 

# importing os module 
import os

# Print the value of
# 'JAVA_HOME'  environment variable 
print("JAVA_HOME:", os.environ['JAVA_HOME')

# Modify the value of
# 'JAVA_HOME'  environment variable 
os.environ['JAVA_HOME'] = '/home / ihritik / jdk-10.0.1'

# Print the modified value of
# 'JAVA_HOME' environment variable
print("Modified JAVA_HOME:", os.environ['JAVA_HOME'])
```

**Output:**

```
JAVA_HOME: /opt/jdk-10.0.1
Modified JAVA_HOME: /home/ihritik/jdk-10.0.1

```

**代码#4:** 添加新的环境变量

```
# Python program to explain os.environ object 

# importing os module 
import os

# Add a new environment variable 
os.environ['GeeksForGeeks'] = 'www.geeksforgeeks.org'

# Get the value of
# Added environment variable 
print("GeeksForGeeks:", os.environ['GeeksForGeeks'])
```

**Output:**

```
GeeksForGeeks: www.geeksforgeeks.org

```

**代码#5:** 访问不存在的环境变量

```
# Python program to explain os.environ object 

# importing os module 
import os

# Print the value of
# 'MY_HOME' environment variable 
print("MY_HOME:", os.environ['MY_HOME']

# If the key does not exists
# it will produce an error
```

**Output:**

```
Traceback (most recent call last):
  File "osenviron.py", line 8, in 
    print("MY_HOME:", os.environ['MY_HOME'])
  File "/usr/lib/python3.6/os.py", line 669, in __getitem__
    raise KeyError(key) from None
KeyError: 'MY_HOME'

```

**代码#6:** 访问不存在的环境变量时处理错误

```
# Python program to explain os.environ object 

# importing os module 
import os

# Method 1
# Print the value of
# 'MY_HOME' environment variable 
print("MY_HOME:", os.environ.get('MY_HOME', "Environment variable does not exist"))

# Method 2
try:
    print("MY_HOME:", os.environ['MY_HOME'])
except KeyError: 
    print("Environment variable does not exist")
```

**Output:**

```
MY_HOME: Environment variable does not exist
Environment variable does not exist

```