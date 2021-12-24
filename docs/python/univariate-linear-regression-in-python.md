# Python 中的一元线性回归

> 原文:[https://www . geesforgeks . org/python 中的单变量-线性回归/](https://www.geeksforgeeks.org/univariate-linear-regression-in-python/)

单变量数据是结果只依赖于一个变量的数据类型。例如，线上的点的数据集可以被认为是单变量数据，其中横坐标可以被认为是输入特征，纵坐标可以被认为是输出/结果。

**例如:**
为线**Y = 2X+3**；
输入特征为 X，结果为 Y。

| X | Y |
| one | five |
| Two | seven |
| three | nine |
| four | Eleven |
| five | Thirteen |

**概念:**
对于单变量线性回归，只有一个输入特征向量。回归线的形式为:

> **Y = b0 + b1 * X**
> 其中，
> b0 和 b1 为回归系数。

因此，正在尝试通过训练模型来预测回归系数 b0 和 b1。

**实用功能**

1.  **预测**T0】
2.  **成本函数:**
    成本函数用回归系数的当前值计算误差百分比。它定量地定义了模型与实际回归系数之间的距离，实际回归系数的误差率最低。

    ```
    def cost(x, y, b0, b1):
        # y is a list of expected value
        errors = []
        for x, y in zip(x, y):
            prediction = predict(x, b0, b1)
            expected = y
            difference = prediction-expected
            errors.append(difference)
        # Now, we have errors for all the observations,

        # for some input, the value of error might be positive 
        # and for some input might be negative, 
        # and if we directly add them up, 
        # the values might cancel out leading to wrong output."

        # Hence, we use concept of mean squared error.
        # in mse, we return mean of square of all the errors.
        mse = sum([e * e for e in errors])/len(errors)
        return mse
    ```

3.  **Cost Derivative**
    After each iteration, the cost is upgraded in proportion to the error. The nature of error is very data sensitive. By data-sensitive i mean the error value changes very fast because we had square in error function. Hence, to make it more tolerant to high values of errors, we derivate the error function.
    The mathematics is as follows:

    ![ \begin{document} \begin{align*} cost(x, y)  &= \frac{1}{m} \left( \sum_{i=1}^{n}\, (prediction(x_i)-y_i)^2 \right) \\ &= \frac{1}{m} \left( \sum_{i=1}^{n}\, (b0+b1*x_i-y_i)^2 \right) \end{align} \vspace{15} \begin{align*} cost\_derivative(x, y)  &= \frac{\partial}{\partial b}\left( \frac{1}{m} \left( \sum_{i=1}^{n}\, (b0+b1*x_i-y_i)^2 \right) \right) \\ &=  \frac{1}{m} \left( \sum_{i=1}^{n}\, \left(\frac{\partial}{\partial b}(b0+b1*x_i-y_i)^2\right)  \right)  \hspace{4ex} ....using DUIS \\ &= \frac{1}{m} \left( \sum_{i=1}^{n}\, \left(2*(b0+b1*x_i-y_i)*x_i^b \right) \right) \\ &=  \frac{1}{m} \left( \sum_{i=1}^{n}\, \left(2*(prediction(x_i)-y_i)*x_i^b \right) \right) \\ \end{align} Where, \newline m = len(x) - is the number of rows in the dataset. \newline $x_i^b$ - is x who's coefficient is b. \newline y = b_0+b_1 x_1 \newline $In this, b_1$ is coefficient of $x_1$ but coefficient of $b_0$ is 1 \[     x_i^b =     \begin{cases}        1 & i=0 \\       x_i & otherwise    \end{cases} \] For this, we append an extra row consisting of 1's for $b_0$. \newline Or, add a switch case to the $cost\_derivative$ function. \newline In our case, we will proceed with switch case. \newline \end{document} ](img/476ee372e936fcef887dfb6306df4289.png "Rendered by QuickLaTeX.com")

    **代码:**

    ```
    def cost_derivative(x, y, b0, b1, i):
        return sum([
                      2*(predict(xi, b0, b1)-yi)*1
                       if i == 0
                       else 2*(predict(xi, b0, b1)-yi)*xi
                       for xi, yi in zip(x, y)
               ])/len(x)
    ```

4.  **Update Coefficients :**
    At each iteration (epoch), the values of the regression coefficient are updated by a specific value wrt to the error from the previous iteration. This updation is very crucial and is the crux of the machine learning applications that you write.
    Updating the coefficients with exact an update of a coefficient is done by penalizing its value with a fraction of error that its previous values caused.
    This fraction is called as learning rate. This defines how fast our model reaches out to point of convergence(point where error is ideally 0).

    ![ \begin{align*} b_i & = b_i - \alpha * \left( \frac{\partial}{\partial b} cost(x, y) \right) \\ & = b_i - \alpha * \left( cost\_derivative(x, y, i) \right) $ \end{align} $b_i = b_i - \alpha * \left( \frac{\partial}{\partial b} cost(x, y) \right) $ ](img/499123bef9d951c56830fb4d0ec469c6.png "Rendered by QuickLaTeX.com")

    Python 函数的相同之处如下:

    ```
    def update_coeff(x, y, b0, b1, i, alpha):
        bi -= alpha * cost_derivative(x, y, b0, b1, i)
        return bi
    ```

5.  **停止迭代:**
    这是用来指定迭代应该在什么时候停止的函数。
    根据用户情况，算法 stop_iteration 一般在以下情况下返回 true:
    1.  **最大迭代次数:**针对指定的迭代次数训练模型。
    2.  **误差值:**根据之前误差的值，算法决定是继续还是停止。
    3.  **精度:**根据模型的最后精度，如果大于上述精度，算法返回 True，
    4.  **杂种:**这个用的比较多。这结合了一个以上的上述条件以及一个特殊的中断选项。特殊休息是训练持续到坏事发生的情况。不好的事情可能包括结果溢出、超过时间限制等。

定义了所有实用函数后，让我们看看伪代码及其实现:

**代码:**

```
x, y is the given data.
(b0, b1) <-- (0, 0)
i = 0
while True:
    if stop_iteration(i):
        break
    else:
        b0 = update_coeff(x, y, b0, b1, 0, alpha)
        b1 = update_coeff(x, y, b0, b1, 1, alpha)
```

**最终 Oop 实现:**

```
class LinearRegressor:
    def __init__(self, x, y, alpha = 0.01, b0 = 0, b1 = 0):
        """ 
            x: input feature
            y: result / target
            alpha: learning rate, default is 0.01
            b0, b1: linear regression coefficient.
        """
        self.i = 0
        self.x = x
        self.y = y
        self.alpha = alpha
        self.b0 = b0
        self.b1 = b1
        if len(x) != len(y):
            raise TypeError("x and y should have same number of rows.")

    def predict(model, x):
        """Predicts the value of prediction based on 
           current value of regression coefficients when input is x"""
        # Y = b0 + b1 * X
        return model.b0 + model.b1 * x

    def cost_derivative(model, i):
        x, y, b0, b1 = model.x, model.y, model.b0, model.b1
        predict = model.predict
        return sum([
            2 * (predict(xi) - yi) * 1
            if i == 0
            else (predict(xi) - yi) * xi
            for xi, yi in zip(x, y)
        ]) / len(x)

    def update_coeff(model, i):
        cost_derivative = model.cost_derivative
        if i == 0:
            model.b0 -= model.alpha * cost_derivative(i)
        elif i == 1:
            model.b1 -= model.alpha * cost_derivative(i)

    def stop_iteration(model, max_epochs = 1000):
        model.i += 1
        if model.i == max_epochs:
            return True
        else:
            return False

    def fit(model):
        update_coeff = model.update_coeff
        model.i = 0
        while True:
            if model.stop_iteration():
                break
            else:
                update_coeff(0)
                update_coeff(1)

if __name__ == '__main__':
    linearRegressor = LinearRegressor(
        x =[i for i in range(12)],
        y =[2 * i + 3 for i in range(12)],
        alpha = 0.03
    )
    linearRegressor.fit()
    print(linearRegressor.predict(12))

    # expects 2 * 12 + 3 = 27
```