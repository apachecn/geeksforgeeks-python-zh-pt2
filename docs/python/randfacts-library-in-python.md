# Python 中的 Randfacts 库

> 原文:[https://www.geeksforgeeks.org/randfacts-library-in-python/](https://www.geeksforgeeks.org/randfacts-library-in-python/)

在本文中，我们将学习生成随机事实的 **Randfacts** python 库。您可以使用 randfacts.get_fact()返回一个随机有趣的事实。

**安装:**

```py
pip install randfacts
```

**打印随机事实的代码:**

## 蟒蛇 3

```py
# code
import randfacts

x = randfacts.get_fact()
print(x)
```

**产量:**

> 美国人每年吃 90 亿只鸡和 1.5 亿头牛，
> 
> 猪和羊，我们用 2600 万只左右的动物做研究，
> 
> 其中 95%是啮齿动物、鸟类和鱼类。

**get_fact** 函数:是接受布尔值的函数。该布尔值确定显式内容过滤器是否打开。如果我们将“真”传递给函数，过滤器将打开(这是默认设置)，如果我们将“假”传递给函数，过滤器将关闭。

**关闭滤镜**

## 蟒 3

```py
# code
import randfacts

x = randfacts.get_fact(False)
print(x)
```