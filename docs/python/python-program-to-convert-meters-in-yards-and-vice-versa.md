# Python 程序以码为单位转换米，反之亦然

> 原文:[https://www . geesforgeks . org/python-程序-转换-米/码-反之亦然/](https://www.geeksforgeeks.org/python-program-to-convert-meters-in-yards-and-vice-versa/)

给定以米或码为单位的距离，这里的任务是生成一个 Python 程序，将以米为单位的距离转换为码，反之亦然。

**示例:**

```
Input: Length in Meter: 245
       Length in Yard : 100

Output: 245 Meter in Yard = 267.9344 
        100 Yards in Meter = 91.4403

Input: Length in Meter: 5
       Length in Yard : 20

Output: 5 Meter in Yard = 5.4680 
        20 Yards in Meter = 18.2881
```

**使用的公式–**

```
1 Meter = 1.09361 Yard
```

从上面的公式来看，1 米相当于 1.09361 码，因此要将米转换为码，只需将米中给出的距离乘以 1.09361，要将码转换为米，我们只需将码中的长度除以 1.09361。

下面是实现。

T2T4

```
meter = 5  # Length in Meter
yard = 20  # Length in Yard

# converting Meter to Yard
meter_to_yard = meter * 1.09361

# converting Yard to meter
yard_to_meter = yard / 1.09361

# printing the output
print("%d Meter in Yard = %.4f " % (meter, meter_to_yard))
print("%d Yard in Meter = %.4f " % (yard, yard_to_meter))
```

T5

**输出:**

> 5 码= 5.4680
> 
> 20 码= 18.2881