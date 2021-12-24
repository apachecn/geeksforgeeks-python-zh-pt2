# 将摄氏温度转换为华氏温度的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-convert-摄氏度-华氏度/](https://www.geeksforgeeks.org/python-program-to-convert-celsius-to-fahrenheit/)

假设温度是摄氏度。任务是转换华氏刻度中的值并显示它。
**例:**

```
Input :
37 
Output :
37.00 Celsius is: 98.60 Fahrenheit

Input :
40
Output :
40.00 Celsius is equivalent to: 104.00 Fahrenheit
```

**逼近:**
以用户输入的摄氏温度为输入，应用摄氏到华氏的转换公式，并显示出来。摄氏温标和华氏温标的关系由:

![fahrenheit = (celsius*1.8) + 32 ](img/6dc75ed25da22bc9a27bbc07427d6a43.png "Rendered by QuickLaTeX.com")

给出，下面是实现。

## 蟒蛇 3

```
# Temperature in celsius degree
celsius = 40

# Converting the temperature to
# fehrenheit using the above
# mentioned formula
fahrenheit = (celsius * 1.8) + 32

# printing the result
print('%.2f Celsius is equivalent to: %.2f Fahrenheit'
      %(celsius, fahrenheit))
```

**输出:**

```
40.00 Celsius is equivalent to: 104.00 Fahrenheit
```