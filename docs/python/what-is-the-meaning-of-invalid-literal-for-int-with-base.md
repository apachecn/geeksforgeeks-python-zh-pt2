# 对于 base = ' '的 int()无效文字是什么意思？

> 原文:[https://www . geeksforgeeks . org/with-base/无效文字的含义是什么](https://www.geeksforgeeks.org/what-is-the-meaning-of-invalid-literal-for-int-with-base/)

当我们传递不适当的参数类型时，会遇到**值错误**。这里，我们讨论的是向`int()`函数传递不正确的参数导致的 ValueError。当我们传递一个浮点数的字符串表示或者除了 int 之外的任何字符串表示时，它会给出一个 ValueError。

**示例 1 :** 基数为 10 的值错误。

```py
# ValueError caused by conversion of 
# String representation of float to int
int('23.5')
```

输出:

```py
ValueError: invalid literal for int() with base 10: '23.5'
```

人们可以认为，在执行上述代码时，小数部分“. 5”应该被截断，代码给出的输出应该只有 23。但是需要注意的一点是 int()函数使用十进制数字系统作为转换 ie 的基础。base = 10 是转换的默认值。在十进制数字系统中，我们有从 0 到 9 的数字，不包括小数(。)和其他字符(字母和特殊字符)。因此，base = 10 的`int()`只能转换 int 的字符串表示，不能转换浮点或字符。

我们可以先用`float()`函数把 float 的字符串表示转换成 float，再用`int()`转换成整数。

```py
print(int(float('23.5')))
```

**输出:**

```py
23
```

**示例 2 :** 在`int()`中传递字母。

```py
int('abc')
```

**输出:**

```py
invalid literal for int() with base 10: 'abc'
```

字符 a、b、c、d、e 和 f 存在于 base =16 系统中，因此只有这些字符以及数字 0 到 9 可以从它们的字符串表示形式转换为十六进制形式的整数。我们必须传递一个值为 16 的参数`base`。

```py
print(int('abc', base = 16))
```

**输出:**

```py
2748
```