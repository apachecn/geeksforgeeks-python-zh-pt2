# Python |运行时提示输入密码并终止，出现错误消息

> 原文:[https://www . geeksforgeeks . org/python-运行时提示输入密码并终止错误消息/](https://www.geeksforgeeks.org/python-prompt-for-password-at-runtime-and-termination-with-error-message/)

假设我们的脚本需要一个密码，但是由于脚本是用于交互使用的，它可能会提示用户输入密码，而不是将其硬编码到脚本中。

Python 的 **getpass 模块**正是做了它需要做的事情。它将允许用户非常容易地提示输入密码，而无需在用户终端上显示键入的密码。

**代码#1:是怎么做到的？**

```py
import getpass
user = getpass.getuser()
passwd = getpass.getpass()

# must write svc_login() 
if svc_login(user, passwd):
    print('Yay !')
else:
    print('Boo !')
```

在上面的代码中，`svc_login()`功能是为进一步处理密码输入而编写的代码。显然，确切的处理是特定于应用程序的。在上面的代码中`getpass.getuser()`没有提示用户输入用户名。相反，根据用户的 shell 环境，或者作为最后手段，根据本地系统的密码数据库(在支持 **pwd** 模块的平台上)，它使用当前用户的登录名。

为了明确提示用户输入用户名，这可能更可靠，使用了内置的输入功能。

```py
user = input('Enter your username: ')
```

同样重要的是要记住，有些系统可能不支持隐藏输入到`getpass()`方法的输入密码。在这种情况下，Python 会在继续下一步之前尽一切可能向用户发出问题预警(即，它会提醒用户密码将以明文形式显示)。

### 执行外部命令并获取其输出–

**代码#2:使用`subprocess.check_output()`功能**

```py
import subprocess
out_bytes = subprocess.check_output(['netstat', '-a'])
```

这将运行指定的命令，并以字节字符串的形式返回其输出。要将结果字节解释为文本，请添加进一步的解码步骤，如下面给出的代码所示–

**代码#3 :**

```py
out_text = out_bytes.decode('utf-8')
```

如果执行的命令返回非零退出代码，则会引发异常。

**代码#4:捕捉错误并获得与退出代码一起创建的输出**

```py
try:
    out_bytes = subprocess.check_output(['cmd', 'arg1', 'arg2'])

except subprocess.CalledProcessError as e:    
    # Output generated before error
    out_bytes = e.output 
    # Return code
    code = e.returncode 
```

默认情况下， <ccode>check_output()只返回写入标准输出的输出。</ccode>

**代码#5:使用 stderr 参数获取标准输出和错误收集**

```py
out_bytes = subprocess.check_output(
        ['cmd', 'arg1', 'arg2'], stderr = subprocess.STDOUT)
```

**代码#6:使用超时参数()执行一个带超时的命令。**

```py
try:
    out_bytes = subprocess.check_output(['cmd', 'arg1', 'arg2'], timeout = 5)
except subprocess.TimeoutExpired as e:
    ...
```

通常，命令是在没有底层外壳(如 sh、bash 等)的帮助下执行的。).相反，所提供的字符串列表被提供给一个低级系统命令，如 os.execve()。对于要由 shell 解释的命令，请使用简单的字符串提供它，并给 shell=True 参数。如果试图让 Python 执行涉及管道、I/O 重定向和其他功能的复杂 shell 命令，这有时会很有用，如下所示–
**代码#7 :**

```py
out_bytes = subprocess.check_output(
        'grep python | wc > out', shell = True)
```

如果参数来源于用户输入，在 shell 下执行命令会带来潜在的安全风险。在这种情况下，`shlex.quote()`函数可用于正确引用包含在 shell 命令中的参数。