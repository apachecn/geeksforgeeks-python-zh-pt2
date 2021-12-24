# Python 中的开关盒(替换)

> 原文:[https://www . geeksforgeeks . org/switch-python 中的案例-替换/](https://www.geeksforgeeks.org/switch-case-in-python-replacement/)

**Python 中 Switch Case 的替换是什么？**

与我们以前使用的其他编程语言不同，Python 没有 switch 或 case 语句。为了绕开这个事实，我们使用[字典映射](https://www.youtube.com/watch?v=z7z_e5-l2yE)。

## 蟒蛇 3

```
# Function to convert number into string
# Switcher is dictionary data type here
def numbers_to_strings(argument):
    switcher = {
        0: "zero",
        1: "one",
        2: "two",
    }

    # get() method of dictionary data type returns
    # value of passed argument if it is present
    # in dictionary otherwise second argument will
    # be assigned as default value of passed argument
    return switcher.get(argument, "nothing")

# Driver program
if __name__ == "__main__":
    argument=0
    print (numbers_to_strings(argument))
```

这段代码类似于 C++中给定的代码:

## 卡片打印处理机（Card Print Processor 的缩写）

```
#include<bits/stdc++.h>
using namespace std;

// Function to convert number into string
string numbers_to_strings(int argument){
    switch(argument) {
        case 0:
            return "zero";
        case 1:
            return "one";
        case 2:
            return "two";
        default:
            return "nothing";
    };
};

// Driver program
int main()
{
    int argument = 0;
    cout << numbers_to_strings(argument);
    return 0;
}
```

**输出:**

```
Zero
```

本文由 [**沙莎克·米什拉(古卢)**](https://auth.geeksforgeeks.org/profile.php?user=Shashank Mishra) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。