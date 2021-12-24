# Python 程序计算工资总额

> 原文:[https://www . geesforgeks . org/python-计算毛工资程序/](https://www.geeksforgeeks.org/python-program-to-calculate-gross-pay/)

总工资是员工在特定时间内扣除任何费用之前的收入。有许多不同的方法来计算工资总额，这取决于员工的报酬。这篇文章描述了两种最常见的方式——计时和工资。

### 时薪员工

如果一个雇员按小时计酬，那么他每工作一小时就得到固定的报酬。因此，如果他每小时拿 100 卢比，工作 8 小时，他的总工资是 800 卢比。每小时员工的总工资必须以周为基础计算。因为一项名为加班的规则，联邦政府的《公平劳动标准法》规定，对于加班，员工必须以不低于正常工资 1.5 倍的速度获得每周工作 40 小时以上的加班费。

**示例:**

> 假设 A 是按小时计酬的员工，他的工资是 100/小时。
> 
> 如果他一周工作 50 小时，那么他将获得额外工作时间的加班费，也就是说，他将获得 10 小时 100 卢比的 1.5 倍工资(50-40)。
> 
> 如果工作时间> 40，则:
> 总工资=(小时工资*40) + (1.5 *小时工资*(工作时间-40))。
> 
> 如果工作 _ 小时< 40     then:
> 总工资总额=小时工资*工作 _ 小时。
> ramu 的工作时间=50 小时，即大于 40 小时。
> 总毛工资= 100 * 40+(1.5)* 100 * 10 =>5500 卢比。

**程序:**

## 蟒蛇 3

```py
def weeklyPaid(hours_worked, wage):
    if hours_worked > 40:
        return 40 * wage + (hours_worked - 40) * wage * 1.5
    else:
        return hours_worked * wage

hours_worked = 50
wage = 100

pay = weeklyPaid(hours_worked, wage)

print(f"Total gross pay: Rs.{pay:.2f} ")
```

**输出:**

```py
Total gross pay: Rs.5500.00 

```

### 受薪雇员

工资通常按年报价，但通常员工按月支付。为了计算受薪员工的总工资，我们需要将年薪除以一年中的支付期数(即他们一年中获得多少分期付款)。

**示例:**

> 让我们假设乙是一名受薪员工，他的年薪是 120 万英镑。
> 如果 B 按月支付，那么总支付额将为 120 万/ 12。
> 
> 总工资= 12/12 = > 10 亿英镑。

**程序:**

## 蟒蛇 3

```py
def getGrossPay(annual_salary, no_of_pay_peroids):
    return float(annual_salary/no_of_pay_peroids)

# driver code

# annual_salary in lakhs
annual_salary = 12
no_of_pay_peroids = 12
pay = getGrossPay(annual_salary, no_of_pay_peroids)

print(f"Total gross pay: Rs.{pay:.2f} lakhs ")
```

**输出:**

```py
Total gross pay: Rs.1.00 lakhs 

```

**时间复杂度:** O (1)