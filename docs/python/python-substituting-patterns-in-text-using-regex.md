# Python–使用正则表达式

替换文本中的模式

> 原文:[https://www . geeksforgeeks . org/python-替换-文本中的模式-使用-regex/](https://www.geeksforgeeks.org/python-substituting-patterns-in-text-using-regex/)

[正则表达式](https://www.geeksforgeeks.org/regular-expression-python-examples-set-1/)(正则表达式)是指从任何基于模式的文本中提取所需的信息。它们也被广泛用于处理基于模式的文本，从而导致文本预处理，并且在实现像**自然语言处理(NLP)** 这样的数字技能方面非常有帮助。

本文通过提供多个例子来演示如何使用正则表达式来替换模式，其中每个例子都是一个独特的场景。理解`re`(正则表达式)模块的`re.sub()`方法对理解给定的解是非常必要的。

`re.sub()`方法对给定字符串执行全局搜索和全局替换。它用于替换字符串中的特定模式。这个函数总共有 5 个参数。

> **语法:** re.sub(模式，repl，字符串，计数=0，标志=0)
> 
> **参数:**
> 模式–要搜索和替换的模式
> repl–要替换模式的字符串
> 字符串–存储模式的变量名称
> 计数–要执行替换的字符数
> 标志–用于修改正则表达式模式的含义
> 
> `**count**`和`**flags**`是可选参数。

**示例 1:特定文本模式的替换**
在本示例中，给定的文本模式将被搜索并替换为字符串。这个想法是使用非常正常的`re.sub()`方法，只有前 3 个参数。

下面是实现。

```py
# Python implementation of substituting a 
# specific text pattern in a string using regex

# importing regex module
import re

# Function to perform
# operations on the strings
def substitutor():

    # a string variable
    sentence1 = "It is raining outside."

    # replacing text 'raining' in the string 
    # variable sentence1 with 'sunny' thus
    # passing first parameter as raining
    # second as sunny, third as the 
    # variable name in which string is stored
    # and printing the modified string
    print(re.sub(r"raining", "sunny", sentence1))

    # a string variable
    sentence2 = "Thank you very very much."

    # replacing text 'very' in the string 
    # variable sentence2 with 'so' thus 
    # passing parameters at their 
    # appropriate positions and printing 
    # the modified string
    print(re.sub(r"very", "so", sentence2))

# Driver Code: 
substitutor()
```

**Output:**

```py
It is sunny outside.
Thank you so so much.

```

> 无论所需模式在字符串中出现多少次，`re.sub()`函数都会用给定的模式替换所有模式。这就是为什么在上面的例子中,“非常”被“所以”所取代。

**示例 2:用特定字符替换字符集**
任务是用给定的字符替换字符集。字符集意味着一系列字符。在`re.sub()`方法中，字符集写在[ ](方括号)内。

在本例中，小写字符集，即[a-z]将被数字 0 替换。下面是实现。

```py
# Python implementation of substituting 
# a character set with a specific character

# importing regex module
import re

# Function to perform
# operations on the strings
def substitutor():

    # a string variable
    sentence = "22 April is celebrated as Earth Day."

    # replacing every lower case characters  
    # in the variable sentence with 0 and 
    # printing the modified string
    print(re.sub(r"[a-z]", "0", sentence))

# Driver Code: 
substitutor()
```

**Output:**

```py
22 A0000 00 0000000000 00 E0000 D00.

```

> 如果需要同时替换小写和大写字符集，那么我们必须以这种方式引入大写字符集:【a-zA-Z】或者**有效的**方式是使用标志。

**示例 3:用特定字符**
替换不区分大小写的字符集在本例中，小写和大写字符都将被给定字符替换。有了**旗帜**的使用，这个任务可以非常轻松的完成。

`re.I`旗代表 re。**忽略**。通过在`re.sub()`方法中引入这个标志，并提及任何一个字符集，即小写或大写，任务就可以完成。

下面是实现。

```py
# Python implementation of case-insensitive substitution
# of a character set with a specific character

# importing regex module
import re

# Function to perform
# operations on the strings
def substitutor():

    # a string variable
    sentence = "22 April is celebrated as Earth Day."

    # replacing both lowercase and
    # uppercase characters with 0 in  
    # the variable sentence by using 
    # flag and printing the modified string 
    print(re.sub(r"[a-z]", "0", sentence, flags = re.I))

# Driver Code: 
substitutor()
```

**Output:**

```py
22 00000 00 0000000000 00 00000 000.

```

**示例 4:最多替换一定数量的字符**
在本例中，替换将最多替换特定数量的字符，而不是整个字符串。要执行这种类型的替换，`re.sub()`方法有一个参数`count`。

通过为该参数提供一个数值，可以控制将要发生替换的字符数。下面是实现。

```py
# Python implementation to perform substitution
# up to a certain number of characters

# importing regex module
import re

# Function to perform
# operations on the strings
def substitutor():

    # a string variable
    sentence = "Follow your Passion."

    # case-insensitive substitution
    # on variable sentence upto  
    # eight characters and printing
    # the modified string
    print(re.sub(r"[a-z]", "0", sentence, 8, flags = re.I))

# Driver Code: 
substitutor()
```

**Output:**

```py
000000 00ur Passion.

```

**示例 5:使用速记字符类的替换和文本的预处理**
Regex 模块为那些在文本预处理过程中非常常见的字符集提供了许多速记字符类。使用速记字符类可以编写高效的代码，并减少记住每个字符集范围的需要。

要获得速记字符类的详细说明，以及如何用 python 编写正则表达式进行文本预处理，请点击这里的。以下是一些常用的速记字符类别:

> \w:匹配字母数字字符
> \W:匹配@、#、'、+、%、–
> \ d:匹配数字字符
> \s:匹配空格字符
> 
> **某些语法的含义:**
> 在一个字符类或集合后添加一个加号(+):重复前面的字符类或集合至少 1 次或更多次。
> 
> 在字符类或字符集后添加星号(*)符号:重复前面的字符类或字符集至少 0 次或更多次。
> 
> 在字符类或字符集之前添加 caret(^符号:在字符串的开头为该字符类或字符集确定匹配位置。
> 
> 在字符类或字符集后添加一个美元符号:在字符串的末尾为该字符类或字符集确定匹配位置。

这个例子演示了使用所提到的速记字符类来替换和预处理文本，以获得干净且无错误的字符串。下面是实现。

```py
# Python implementation of Substitution using 
# shorthand character class and preprocessing of text

# importing regex module
import re

# Function to perform
# operations on the strings
def substitutor():

    # list of strings
    S = ["2020 Olympic games have @# been cancelled",
     "Dr Vikram Sarabhai was +%--the ISRO’s first chairman",
     "Dr Abdul            Kalam, the father      of India's missile programme"]

    # loop to iterate every element of list
    for i in range(len(S)):

        # replacing every non-word character with a white space
        S[i] = re.sub(r"\W", " ", S[i])

        # replacing every digit character with a white space
        S[i] = re.sub(r"\d", " ", S[i])

        # replacing one or more white space with a single white space
        S[i] = re.sub(r"\s+", " ", S[i])

        # replacing alphabetic characters which have one or more 
        # white space before and after them with a white space
        S[i] = re.sub(r"\s+[a-z]\s+", " ", S[i], flags = re.I)

        # substituting one or more white space which is at 
        # beginning of the string with an empty string
        S[i] = re.sub(r"^\s+", "", S[i])

        # substituting one or more white space which is at
        # end of the string with an empty string
        S[i] = re.sub(r"\s+{content}quot;, "", S[i])

    # loop to iterate every element of list
    for i in range(len(S)):

        # printing each modified string
        print(S[i])

# Driver Code: 
substitutor()    
```

**Output:**

```py
Olympic games have been cancelled
Dr Vikram Sarabhai was the ISRO first chairman
Dr Abdul Kalam the father of India missile programme

```