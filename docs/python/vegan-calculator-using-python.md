# 使用 Python 的素食计算器

> 原文:[https://www . geesforgeks . org/vegan-calculator-use-python/](https://www.geeksforgeeks.org/vegan-calculator-using-python/)

纯素食饮食只包含植物性食物。它不含任何动物产品，如肉、蛋、奶、蜂蜜等。素食主义者的生活方式将此推断为不使用由动物产品如皮革、羊毛、丝绸等制成的日常用品。观察这种生活方式的人被称为**素食主义者**。
素食对健康有很多好处。它还具有多重环境效益。根据多项研究，一个纯素食者在一个月内可以节省:

*   1100 加仑或 4164 升水
*   45 磅或 20.4 公斤谷物
*   30 平方英尺或 2.7 平方米的森林
*   20 磅或 9 千克二氧化碳

**算法:**

1.  将年份转换为月份，并将其添加到月份中。
2.  根据上面提到的值计算保存的项目数量。
3.  使用 round()方法舍入值，然后打印它们。

## 蟒蛇 3

```
# function to calculate the amount of
# things saved by being vegan
def vegan_calculator(m, y):

    # converting years to months
    months_vegan = y * 12 + m

    # calculating things saved
    water = 4164 * months_vegan
    grain = 20.4 * months_vegan
    forest = 2.7 * months_vegan
    co2 = 9 * months_vegan

    # printing the statistics
    print("You have been vegan for " + str(months_vegan) + " months.")
    print("\nYou have successfully saved :")
    print(str(water) + " litres of water")
    print(str(round(grain)) + " kgs of grain")
    print(str(round(forest)) + " square metres of forest")
    print(str(round(co2)) + " kgs of carbon dioxide")

# Driver code
if __name__=="__main__":
    months = 4
    years = 2
    vegan_calculator(months, years)
```

**输出:**

```
You have been vegan for 28 months.

You have successfully saved :
116592 litres of water
571 kgs of grain
76 square metres of forest
252 kgs of carbon dioxide
```