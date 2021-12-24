# Python 中的递归

> 原文:[https://www.geeksforgeeks.org/recursion-in-python/](https://www.geeksforgeeks.org/recursion-in-python/)

术语[递归](https://www.geeksforgeeks.org/recursion/#:~:text=The%20process%20in%20which%20a, can%20be%20solved%20quite%20easily.)可以定义为根据事物本身来定义事物的过程。简单来说，就是函数直接或间接调用自身的过程。

![img](img/c1dfe53d4c7e11440ffd0d94dfafbafb.png)

使用递归的优点

*   一个复杂的函数可以利用递归分解成更小的子问题。
*   通过递归创建序列比利用嵌套迭代更简单。
*   递归函数使代码看起来简单而有效。

使用递归的缺点

*   大量的内存和时间是通过递归调用获得的，这使得它的使用成本很高。
*   递归函数很难调试。
*   递归背后的推理有时很难思考清楚。

**语法:**

```py
def func(): **例 1: ** 
斐波那契数列是 0，1，1，2，3，5，8 的整数序列....

```
# Program to print the fibonacci series upto n_terms

# Recursive function
def recursive_fibonacci(n):
   if n <= 1:
       return n
   else:
       return(recursive_fibonacci(n-1) + recursive_fibonacci(n-2))

n_terms = 10

# check if the number of terms is valid
if n_terms <= 0:
   print("Invalid input ! Please input a positive value")
else:
   print("Fibonacci series:")
   for i in range(n_terms):
       print(recursive_fibonacci(i))
```py

**输出:**

```
Fibonacci series:
0
1
1
2
3
5
8
13
21
34

```py

**例 2:**
6 的阶乘表示为 6！= 1*2*3*4*5*6 = 720.

```
# Program to print factorial of a number 
# recursively.

# Recursive function
def recursive_factorial(n):  
   if n == 1:  
       return n  
   else:  
       return n * recursive_factorial(n-1)  

# user input
num = 6

# check if the input is valid or not
if num < 0:  
   print("Invalid input ! Please enter a positive number.")  
elif num == 0:  
   print("Factorial of number 0 is 1")  
else:  
   print("Factorial of number", num, "=", recursive_factorial(num)) 
```py

**输出:**

```
Factorial of number 6 = 720
```py

什么是尾递归？一种独特的递归类型，其中函数的最后一个过程是递归调用。递归可以通过在当前堆栈帧中执行请求并返回输出而不是生成新的堆栈帧来自动完成。尾部递归可以被编译器优化，这使得它比非尾部递归函数更好。**利用尾部递归函数代替非尾部递归函数优化程序是否可能？** 
考虑下面给出的函数，为了计算 n 的阶乘，我们可以观察到这个函数起初看起来像一个尾部递归的函数，但是它是一个非尾部递归的函数。如果我们仔细观察，可以看到 recury _ factor(n-1)返回的值用在 recury _ factor(n)中，所以对 recury _ factor(n-1)的调用并不是 recury _ factor(n)做的最后一件事。

```
# Program to calculate factorial of a number
# using a Non-Tail-Recursive function. 

# non-tail recursive function
def Recur_facto(n): 

    if (n == 0): 
        return 1

    return n * Recur_facto(n-1) 

# print the result
print(Recur_facto(6))
```py

**输出:**

```
720
```py

我们可以把给定的函数 Recur _ facto 写成尾部递归函数。我们的想法是再使用一个参数，在第二个参数中，我们容纳阶乘的值。当 n 达到 0 时，返回所需数字的阶乘的最终值。

```
# Program to calculate factorial of a number
# using a Tail-Recursive function.

# A tail recursive function 
def Recur_facto(n, a = 1): 

    if (n == 0): 
        return a 

    return Recur_facto(n - 1, n * a) 

# print the result
print(Recur_facto(6))
```py

**输出:**

```
720
```py

-->
```