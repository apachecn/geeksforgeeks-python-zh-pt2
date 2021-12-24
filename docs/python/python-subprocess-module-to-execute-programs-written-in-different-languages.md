# 执行不同语言编写的程序的 Python 子流程模块

> 原文:[https://www . geesforgeks . org/python-子流程-模块到执行-程序-用不同语言编写/](https://www.geeksforgeeks.org/python-subprocess-module-to-execute-programs-written-in-different-languages/)

Python 中存在的子进程模块(2.x 和 3.x)用于通过创建新的进程，通过 Python 代码运行新的应用程序或程序。它还有助于获得输入/输出/错误管道以及各种命令的退出代码。

为了使用 Python 执行不同的程序，使用了子流程模块的两个功能:

> **1 . subprocess . check _ call(args，* stdin = None，stdout=None，stderr=None，shell=False)**
> **参数:**
> args =要执行的命令。几个命令可以作为字符串传递，用“；”分隔。
> stdin =作为(os.pipe())传递的标准输入流的值。
> 标准输出=从标准输出流获得的输出值。
> 标准误差=从标准误差流中获得的误差值(如果有)。
> shell =布尔参数。如果为真，则通过新的外壳环境执行命令。
> **返回值:**
> 函数返回命令的返回码。如果返回代码为零，函数将简单地返回(命令成功执行)，否则将引发名为 ProcessError 的错误。
> 
> **2 . subprocess . check _ output(args，* stdin = None，stderr=None，shell=False，universal _ newlines = False)**
> **参数:**
> args =要执行的命令。几个命令可以作为字符串传递，用“；”分隔。
> stdin =作为管道(os.pipe())传递的标准输入流的值。
> 标准输出=从标准输出流获得的输出值。
> 标准误差=从标准误差流中获得的误差值(如果有)。
> shell =布尔参数。如果为真，则通过新的外壳环境执行命令。
> universal _ new lines =布尔参数。如果为 true，则以通用换行符模式打开包含 stdout 和 stderr 的文件。
> **返回值:**
> 函数返回命令的返回码。如果返回代码为零，函数只以字节字符串的形式返回输出(命令成功执行)，否则将引发名为 ProcessError 的错误。

让我们考虑以下例子:

**C 程序:**

```py
#include<stdio.h>
int main()
{
    printf("Hello World from C");

    // returning with any other non zero value
    // would result in an exception
    // when called from python
    return 0;
}
```

**C++程序:**

```py
#include <iostream>
using namespace std;
int main()
{
    int a, b;
    cin >> a >> b;
    cout << "Hello World from C++.Values are:" << a << " " << b;
    return 0;
}
```

**Java 程序:**

```py
class HelloWorld {
    public static void main(String args[])
    {
        System.out.print("Hello World from Java.");
    }
}
```

**Python 3 code to execute the above programs:**

```py
# Python 3 program to demonstrate subprocess 
# module

import subprocess
import os

def excuteC():

    # store the return code of the c program(return 0)
    # and display the output
    s = subprocess.check_call("gcc HelloWorld.c -o out1;./out1", shell = True)
    print(", return code", s)

def executeCpp():

    # create a pipe to a child process
    data, temp = os.pipe()

    # write to STDIN as a byte object(convert string
    # to bytes with encoding utf8)
    os.write(temp, bytes("5 10\n", "utf-8"));
    os.close(temp)

    # store output of the program as a byte string in s
    s = subprocess.check_output("g++ HelloWorld.cpp -o out2;./out2", stdin = data, shell = True)

    # decode s to a normal string
    print(s.decode("utf-8"))

def executeJava():

    # store the output of
    # the java program
    s = subprocess.check_output("javac HelloWorld.java;java HelloWorld", shell = True)
    print(s.decode("utf-8"))

# Driver function
if __name__=="__main__":
    excuteC()    
    executeCpp()
    executeJava()
```

**输出:**

```py
Hello World from C, return code 0
Hello World from C++. Values are:5 10
Hello World from Java.

```

**注意:**虽然子流程模块独立于 OS，但这些命令必须只在 Linux 环境中执行。另外，根据 Python 文档，如果与不可信的输入结合，传递 shell=True 可能会带来安全隐患。