# 检查字符串是否包含任何特殊字符的程序

> 原文:[https://www . geesforgeks . org/python-program-check-string-contains-special-character/](https://www.geeksforgeeks.org/python-program-check-string-contains-special-character/)

给定一个字符串，任务是检查该字符串是否包含任何特殊字符(定义的特殊字符集)。如果发现任何特殊字符，不要接受该字符串。

**示例:**

```
Input : Geeks$For$Geeks
Output : String is not accepted.

Input : Geeks For Geeks
Output : String is accepted

```

**做法:**把我们不想要的所有特殊字符做成一个正则表达式(regex)对象，然后在 search 方法中传递一个字符串。如果字符串中的任何一个字符与正则表达式对象匹配，则搜索方法返回匹配对象，否则返回无。

下面是实现:

## C++

```
// C++ program to check if a string 
// contains any special character

// import required packages
#include <iostream> 
#include <regex> 
using namespace std; 

// Function checks if the string 
// contains any special character
void run(string str)
{

    // Make own character set 
    regex regx("[@_!#$%^&*()<>?/|}{~:]");

    // Pass the string in regex_search 
    // method
    if(regex_search(str, regx) == 0)
        cout << "String is accepted";
    else
        cout << "String is not accepted.";
} 

// Driver Code 
int main() 
{ 

    // Enter the string 
    string str = "Geeks$For$Geeks"; 

    // Calling run function
    run(str); 

    return 0; 
}

// This code is contributed by Yash_R
```

## 蟒蛇 3

```
# Python3 program to check if a string
# contains any special character

# import required package
import re

# Function checks if the string
# contains any special character
def run(string):

    # Make own character set and pass 
    # this as argument in compile method
    regex = re.compile('[@_!#$%^&*()<>?/\|}{~:]')

    # Pass the string in search 
    # method of regex object.    
    if(regex.search(string) == None):
        print("String is accepted")

    else:
        print("String is not accepted.")

# Driver Code
if __name__ == '__main__' :

    # Enter the string
    string = "Geeks$For$Geeks"

    # calling run function 
    run(string)
```

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```
<?Php
// PHP program to check if a string 
// contains any special character 

// Function checks if the string 
// contains any special character 
function run($string)
{
    $regex = preg_match('[@_!#$%^&*()<>?/\|}{~:]', 
                                         $string);
    if($regex) 
        print("String is accepted"); 

    else
        print("String is not accepted.");
} 

// Driver Code 

// Enter the string 
$string = 'Geeks$For$Geeks';

// calling run function
run($string);

// This code is contributed by Aman ojha
?>
```

**输出:**

```
String is not accepted.
```