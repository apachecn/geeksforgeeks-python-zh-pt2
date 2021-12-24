# Python |集合 6(命令行和变量参数)

> 原文:[https://www.geeksforgeeks.org/python-set-6-arguments/](https://www.geeksforgeeks.org/python-set-6-arguments/)

之前的 python 文章([第 1 集](https://www.geeksforgeeks.org/python-the-new-generation-language/) | [第 2 集](https://www.geeksforgeeks.org/python-set-2-variables-expressions-conditions-and-functions/) | [第 3 集](https://www.geeksforgeeks.org/python-set-3-strings-lists-tuples-iterations/) | [第 4 集](https://www.geeksforgeeks.org/python-set-4-dictionary-keywords-python/) | [第 5 集](https://www.geeksforgeeks.org/python-exception-handling/) )
本文主要关注 Python 中函数的命令行参数以及变量参数(args 和 kwargs)。

## 命令行参数

到目前为止，我们已经在 python 中使用 raw_input()或 input()[对于整数]进行了输入。还有一种方法使用命令行参数。每当我们想要在脚本开始之前给出输入时，必须给出命令行参数，而另一方面，raw_input()用于在 python 程序/脚本运行时获得输入。

例如，在 UNIX 环境中，“ls”命令的参数“-a”和“-l”给出不同的结果。

python 中的命令行参数可以通过使用“sys”模块或“argparse”模块来处理。

```
# Python code to demonstrate the use of 'sys' module
# for command line arguments

import sys

# command line arguments are stored in the form
# of list in sys.argv
argumentList = sys.argv
print argumentList

# Print the name of file
print sys.argv[0]

# Print the first argument after the name of file
print sys.argv[1]
```

输出:

```
['program1.py', 'test', '1']
program1.py
test

```

**注意:**上面的代码只在命令行上运行。鉴于该程序已保存为程序 1.py
`python program1.py test 123` 
，我们需要触发以下命令。请注意上述程序的以下几点:

*   sys.argv 采用列表形式的命令行参数。
*   列表中的第一个元素是文件名。
*   The arguments always come in the form of a string even if we type an integer in the argument list. We need to use int() function to convert the string to integer.

    我们可以使用命令行参数来编写执行常用任务的程序。例如，我们需要多次求阶乘。我们可以将下面的程序保存在计算机中一个名为 factorial.py 的文件中，只需编写获取一个数的阶乘的命令，比如 5，就可以得到输出。
    `python factorial.py 5`

    ```
    import sys
    from math import factorial

    print factorial(int(sys.argv[1]))
    ```

    ## 可变参数

    ### args(*)和 kwargs(**)

    “args”和“kwargs”都用于获取函数中任意数量的参数。

    **args 会以列表的形式给我们所有的函数参数，kwargs 会给我们除了形式参数对应的关键字参数以外的所有关键字参数作为字典。**

    ```
    # Python program to illustrate the use of args which
    # multiplies all the values given to the function as parameter

    def multiplyAll(*values):
        mul = 1 

        # values(args) will be in the form of tuple
        print values
        print "Type = ", type(values)

        # Multiplying the all the parameters and return the result
        for i in values:
            mul = mul * i

        return mul

    # Driver program to test above function

    # Multiply two numbers using above function
    ans = multiplyAll(1,2)
    print "The multiplication of 1 and 2 is ", ans

    # Multiply 5 numbers using above function
    ans = multiplyAll(3, 4, 5, 6, 7)
    print "The multiplication of 3 to 7 is ", ans
    ```

    输出:

    ```
    (1, 2)
    Type =  
    The multiplication of 1 and 2 is  2
    (3, 4, 5, 6, 7)
    Type =  
    The multiplication of 3 to 7 is  2520

    ```

    注意**参数**用单星表示，**参数**在函数形式参数前用两颗星表示。

    ```
    # Program to illustrate the use of kwargs in Python

    # Function that print the details of a student
    # The number of details per student may vary
    def printDetails(**details):

        # Variable 'details' contains the details in the
        # form of dictionary
        print "Parameter details contains"
        print details 
        print "Type = ", type(details)

        # Print first name 
        print "First Name = ", details['firstName']

        # Print the department of student
        print "Department = ", details['department']
        print "" # Extra line break

    # Driver program to test above function

    # Calling the function with three arguments
    printDetails(firstName = "Nikhil", 
                 rollNumber = "007",
                 department = "CSE")

    # Calling the function with two arguments
    printDetails(firstName = "Abhay",
                 department = "ECE")
    ```

    输出:

    ```
    Parameter details contains
    {'department': 'CSE', 'rollNumber': '007', 'firstName': 'Nikhil'}
    Type =  
    First Name =  Nikhil
    Department =  CSE

    Parameter details contains
    {'department': 'ECE', 'firstName': 'Abhay'}
    Type =  
    First Name =  Abhay
    Department =  ECE

    ```

    请**注意**如果在函数中同时使用 args 和 kwargs，那么 args 参数必须在 kwarg 参数之前。
    示例:

    ```
    # Function containing both args and kwargs
    def cheeseshop(kind, *arguments, **keywords):
        print "-- Do you have any", kind, "?"
        print "-- I'm sorry, we're all out of", kind
        for arg in arguments:
            print arg
        print "-" * 40
        keys = sorted(keywords.keys())
        for kw in keys:
            print kw, ":", keywords[kw]

    # Driver program to test above function
    cheeseshop("Burger", "It's very funny, sir.",
               "It's really very, VERY funny, sir.",
               shopkeeper='Michael Palin',
               client="John Cleese",
               sketch="Cheese Shop Sketch")
    ```

    本文由 [Nikhil Kumar Singh](https://www.linkedin.com/in/nikhil-kumar-singh-15220579)

    供稿，如发现有不正确之处，或想分享以上讨论话题的更多信息，请写评论