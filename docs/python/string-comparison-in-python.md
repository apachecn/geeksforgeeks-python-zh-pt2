# Python 中的字符串比较

> 原文:[https://www.geeksforgeeks.org/string-comparison-in-python/](https://www.geeksforgeeks.org/string-comparison-in-python/)

让我们看看如何比较 Python 中的[字符串](https://www.geeksforgeeks.org/python-strings/)。

**方法 1:** 使用 [**关系运算符**](https://www.geeksforgeeks.org/relational-operators-in-python/)

关系运算符比较从第零个索引到字符串末尾的字符串的字符的 Unicode 值。然后根据使用的运算符返回一个布尔值。

**示例:**

> “极客”==“极客”将返回 True，因为所有字符的 Unicode 都是相同的
> 
> 在“geek”和“Geek”的情况下，因为 G 的 unicode 是\u0047，G 的 unicode 是\ u 0067
> “Geek”<“Geek”将返回 True，而
> “Geek”>“Geek”将返回 False

## 蟒蛇 3

```
print("Geek" == "Geek")
print("Geek" < "geek")
print("Geek" > "geek")
print("Geek" != "Geek")
```

**输出:**

```
True
True
False
False

```

**方法二:**使用[T3 是 T5，](https://www.geeksforgeeks.org/python-membership-identity-operators-not-not/)[T7 不是 T9】](https://www.geeksforgeeks.org/python-membership-identity-operators-not-not/)

**= =**运算符比较两个操作数的值，并检查值是否相等。而 **是** 运算符，检查两个操作数是否引用同一个对象。同样的也是如此！=而**不是**。

让我们用一个例子来理解这一点:

## 蟒蛇 3

```
str1 = "Geek"
str2 = "Geek"
str3 = str1

print("ID of str1 =", hex(id(str1)))
print("ID of str2 =", hex(id(str2)))
print("ID of str3 =", hex(id(str3)))
print(str1 is str1)
print(str1 is str2)
print(str1 is str3)

str1 += "s"
str4 = "Geeks"

print("\nID of changed str1 =", hex(id(str1)))
print("ID of str4 =", hex(id(str4)))
print(str1 is str4)
```