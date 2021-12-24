# Q-学习数学背景

> 原文:[https://www . geesforgeks . org/q-learning-数学-background/](https://www.geeksforgeeks.org/q-learning-mathematical-background/)

**先决条件:** [问学](https://www.geeksforgeeks.org/q-learning-in-python/)。

在下面的推导中，将使用先决条件文章中定义的符号。
Q 学习技术基于**贝尔曼方程**。

![v(s) = E(R_{t+1}+\lambda v(S_{t+1})|S_{t}=s)](img/196b4ce9d147739b7c2ef6318dc28897.png "Rendered by QuickLaTeX.com")
在哪里，
**E:期望
**t+1** :下一状态
**![\lambda](img/73aa9bb7ff52ad1f2fda1ba95744b076.png "Rendered by QuickLaTeX.com")** :折扣系数**

用 Q 值的形式重新表述上述等式:-

![Q^{\pi}(s,a) = E(r_{t+1}+\lambda r_{t+2}+\lambda ^{2}r_{t+3}+...|S_{t}=s,A_{t}=a)](img/ab8be428077a7abe7f0151044755ebb3.png "Rendered by QuickLaTeX.com")

![= E_{s'}(r_{t}+\lambda Q^{\pi}(s',a')|S_{t}=s,A_{t}=a)](img/e22d1ff9335d83884862dbb6c791de56.png "Rendered by QuickLaTeX.com")

**最佳 Q 值**由下式给出

![Q^{*}(s,a) = E_{s'}(r_{t}+\lambda max_{a'}Q^{*}(s',a')|S_{t}=s,A_{t}=a)](img/15ca58b3e107a6f7f3da50e78b7aecd4.png "Rendered by QuickLaTeX.com")

**策略迭代:**是确定模型最优策略的过程，包括以下两个步骤:-

1.  **策略评估:**此过程使用从上一个策略改进步骤中获得的贪婪策略来估计长期奖励函数的值。
2.  **策略改进:**该过程使用最大化每个状态的 V 的动作来更新策略。重复这个过程，直到实现收敛。

**涉及的步骤:-**

*   **Initialization:**

    ![V(s)](img/41757523a21875cb67cd266528a90562.png "Rendered by QuickLaTeX.com") =任意实数
    ![\pi(s)](img/8f75ed660c0c216387fb132b1373e629.png "Rendered by QuickLaTeX.com") =任意选择的任意 A(s)

*   **政策评估:**

    ```py

    while(![\Delta > \theta](img/3b3eacf285257aff6879850cb3efe798.png "Rendered by QuickLaTeX.com"))
    {
        for each s in S
        {    

        }
    }

    ```

*   **政策改善:**

    ```py

    while(true)
        for each s in S
        {

            if(![a\neq \pi (s)](img/e1d193bf909a8de80d4da26bcb6cfa3f.png "Rendered by QuickLaTeX.com"))

            if(![isPolicyStable == true](img/47e0d59471729d4df362ab76b6cdbe1a.png "Rendered by QuickLaTeX.com"))
                break from both loops
        }
    return V,![\pi](img/e43e09d6003d9d39fa5266475445a72c.png "Rendered by QuickLaTeX.com")

    ```

*   **Value Iteration:** This process updates the function V according to the **Optimal Bellman Equation**.

    ![v_{*}(s) = max_{a}E(R_{t+1}+\gamma v_{*}(S_{t+1})|S_{t}=s,A_{t}=a)](img/f078af333d0be63f255446ca4211e686.png "Rendered by QuickLaTeX.com")

**工作步骤:**

*   **初始化:**用任意随机实数初始化数组 V。
*   **计算最优值:**

    ```py

    while(![\Delta > \theta](img/3b3eacf285257aff6879850cb3efe798.png "Rendered by QuickLaTeX.com"))
    {
        for each s in S
        {

        }
    }

    return ![\pi](img/e43e09d6003d9d39fa5266475445a72c.png "Rendered by QuickLaTeX.com")

    ```