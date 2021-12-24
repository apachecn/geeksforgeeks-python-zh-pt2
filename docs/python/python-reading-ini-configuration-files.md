# Python | Reading。ini 配置文件

> 原文:[https://www . geesforgeks . org/python-reading-ini-configuration-files/](https://www.geeksforgeeks.org/python-reading-ini-configuration-files/)

本文旨在读取以常见`.ini`配置文件格式编写的配置文件。**配置解析器**模块可以用来读取配置文件。

**代码#1:配置文件**

```
abc.ini

; Sample configuration file
[installation]
library = %(prefix)s/lib
include = %(prefix)s/include
bin = %(prefix)s/bin
prefix = /usr/local

# Setting related to debug configuration
[debug]
pid-file = /tmp/spam.pid
show_warnings = False
log_errors = true
[server]
nworkers: 32
port: 8080
root = /www/root
signature:
```

**代码#2:读取文件并提取值。**

```
from configparser import ConfigParser

configur = ConfigParser()
print (configur.read('config.ini'))

print ("Sections : ", configur.sections())
print ("Installation Library : ", configur.get('installation','library'))
print ("Log Errors debugged ? : ", configur.getboolean('debug','log_errors'))
print ("Port Server : ", configur.getint('server','port'))
print ("Worker Server : ", configur.getint('server','nworkers'))

```

**输出:**

```
['config.ini']
Sections : ['installation', 'debug', 'server']
Installation Library : '/usr/local/lib'
Log Errors debugged ? : True
Port Server : 8080
Worker Server : 32

```

也可以使用`cfg.write()`方法修改配置并写回文件。

**代码#3 :**

```
configur.set('server','port','9000')
configur.set('debug','log_errors','False')

import sys
configur.write(sys.stdout)
```

**输出:**

```
[installation]
library = %(prefix)s/lib
include = %(prefix)s/include
bin = %(prefix)s/bin
prefix = /usr/local

[debug]
log_errors = False
show_warnings = False

[server]
port = 9000
nworkers = 32
pid-file = /tmp/spam.pid
root = /www/root

```

*   配置文件非常适合为程序指定配置数据。在每个配置文件中，值被分成不同的部分(例如，“安装”、“调试”和“服务器”)。
*   然后，每个部分都有该部分中各种变量的特定值。出于同样的目的，配置文件和使用 Python 源文件之间有一些显著的区别。
*   首先，语法更加宽松和“草率”

配置文件中使用的名称也不区分大小写，如下面的代码所示–

```
configur.get('installation','PREFIX')

configur.get('installation','prefix')
```

**输出:**

```
'/usr/local'
'/usr/local'
```

解析值时，像 getboolean()这样的方法会寻找任何合理的值。例如，这些都是等价的。

```
log_errors = true
log_errors = TRUE
log_errors = Yes
log_errors = 1
```

配置记录和 Python 代码之间最值得注意的对比是，与脚本相反，配置文件不是以自上而下的方式执行的。相反，文件被完全读取。变量替换极有可能在事后进行。例如，前缀变量被分配在碰巧使用它的不同变量之后并没有什么区别。

```
[installation]
library = %(prefix)s/lib
include = %(prefix)s/include
bin = %(prefix)s/bin
prefix = /usr/local
```

可以一起读取多个配置文件，并且可以使用 ConfigParser 将它们的结果合并到一个配置中，这使得它非常特别。

示例–用户创建了自己的配置文件，看起来像。

```
; ~/.config.ini
[installation]
prefix = /Users/beazley/test
[debug]
log_errors = False
```

通过单独读取该文件，可以将其与以前的配置合并

**代码#4 :**

```
import os

# Previously read configuration
print (configur.get('installation', 'prefix'))

# Merge in user-specific configuration
print (configur.read(os.path.expanduser('~/.config.ini')))
print (configur.get('installation', 'prefix'))
print (configur.get('installation', 'library'))

print (configur.getboolean('debug', 'log_errors'))
```

**输出:**

```
'/usr/local' 
['/Users/HP/.config.ini']
'/Users/HP/test'
'/Users/HP/test/lib'
False

```