# Python 程序计算加速度、最终速度、初速度和时间

> 原文:[https://www . geesforgeks . org/python-计算程序-加速度-最终速度-初始速度-时间/](https://www.geeksforgeeks.org/python-program-to-calculate-acceleration-final-velocity-initial-velocity-and-time/)

这里我们可以用公式 a = (v-u)/t 求出加速度(a)、最终速度(v)、初速度(u)和时间(t)。

首先，为所有四种类型的计算定义函数，其中它们将接受三个输入，并在三个不同的变量中赋值。然后，使用加速度公式计算第四个值，并返回计算值。我们将在不同的方法中使用相同的加速度公式。

**进场:**

*   在第一种方法中，我们将通过使用公式**“u =(v-a * t)”**来找到初始速度
*   在第二种方法中，我们将通过使用公式**“v = u+a * t”**来找到最终速度
*   在第三种方法中，我们将通过使用公式**“a =(v–u)/t”**来找到加速度
*   在第四种方法中，我们将使用公式**“t =(v–v)/a”**来寻找时间

**例 1:** 计算初始速度(u)。

## 蟒蛇 3

```py
# code
# Enter final velocity in m/s:
finalVelocity = 10

# Enter acceleration in m per second square
acceleration = 9.8

#Enter time taken in second
time = 1
initialVelocity = finalVelocity - acceleration * time
print("Initial velocity = ", initialVelocity)
```

**输出:**

```py
Initial velocity =  0.1999999999999993
```

**例 2:** 计算最终速度(v)。

## 蟒蛇 3

```py
# code
# initial velocity in m/s:
initialVelocity = 10

# acceleration in m per second square
acceleration = 9.8

# time taken in second
time = 1
finalVelocity = initialVelocity + acceleration * time
print("Final velocity = ", finalVelocity)
```

**输出:**

```py
Final velocity =  19.8
```

**例 3:** 计算加速度(a)。

## 蟒蛇 3

```py
#code
# initial velocity in m/s
initialVelocity = 0

# final velocity in m/s
finalVelocity = 9.8

# time in second
time = 1

acceleration = (finalVelocity - initialVelocity) / time
print("Acceleration = ", acceleration)
```

**输出:**

```py
Acceleration =  9.8
```

**例 4:** 计算时间(t)。

## 蟒蛇 3

```py
# code
#final velocity in m/s
finalVelocity = 10

#initial velocity in m/s
initialVelocity = 0

#acceleration in meter per second square
acceleration = 9.8

time = (finalVelocity - initialVelocity) / acceleration
print("Time taken = ", time)
```

**输出:**

```py
Time taken =  1.0204081632653061
```