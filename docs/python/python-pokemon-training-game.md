# Python |神奇宝贝训练游戏

> 原文:[https://www.geeksforgeeks.org/python-pokemon-training-game/](https://www.geeksforgeeks.org/python-pokemon-training-game/)

**问题:**
你是一个神奇宝贝训练师。每个神奇宝贝都有自己的力量，用一个正整数来描述。当你旅行的时候，你看着神奇宝贝，你抓住了每一个。每次捕捉后，你必须显示到目前为止捕捉到的神奇宝贝的最大和最小力量。你必须有线性时间复杂度。所以排序在这里没用。尝试最小化额外的空间复杂度。
 **举例:**
假设你抓到了 3 8 9 7 的神奇宝贝。那么输出应该是
3 3
3 8
3 9
3 9

```py
Input : 
The single line describing powers of N Pokémon caught. 

Output : 
N lines stating minimum power so far and maximum power
so far separated by single space

```

**代码:Python 代码实现口袋妖怪训练游戏**

```py
# python code to train pokemon
powers = [3, 8, 9, 7]

mini, maxi = 0, 0

for power in powers:
    if mini == 0 and maxi == 0:
        mini, maxi = powers[0], powers[0]
        print(mini, maxi)
    else:
        mini = min(mini, power)
        maxi = max(maxi, power)
        print(mini, maxi)

# Time Complexity is O(N) with Space Complexity O(1)
```

**输出:**

```py
3 3
3 8
3 9
3 9
```