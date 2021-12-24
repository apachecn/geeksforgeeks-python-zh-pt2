# Python–tessentrflow . grad _ pass _ through()

> 原文:[https://www . geesforgeks . org/python-tessentrflow-grad _ pass _ through/](https://www.geeksforgeeks.org/python-tesnsorflow-grad_pass_through/)

TensorFlow 是谷歌设计的开源 Python 库，用于开发机器学习模型和深度学习神经网络。

**grad_pass_through()** 用于创建 grad-pass-through 操作，具有按功能传递的正向行为。

> **语法:**tensorflow . grad _ passs _ through(f)
> 
> **参数:**
> 
> *   **f:** 是返回张量或张量嵌套结构的函数。
> 
> **返回:**它返回一个函数 h(x)，该函数返回与 f(x)相同的值，并且其梯度与恒等式函数的梯度相同。

**例 1:**

## 蟒蛇 3

```py
# Importing the library
import tensorflow as tf

# Initializing the Tensor
x = tf.Variable(2.0, name ="x")
z = tf.Variable(4.0, name ="z")

with tf.GradientTape() as gfg:
  # y will evaluate to 16.0 i.e 4**2
  y = tf.grad_pass_through(x.assign)(z**2)

# res will evaluate to 8.0
res = gfg.gradient(y, z)

# Printing result
print("y: ", y)
print("res: ", res)
```

**输出:**

```py
y:  tf.Tensor(16.0, shape=(), dtype=float32)
res:  tf.Tensor(8.0, shape=(), dtype=float32)
```

**例 2:**

## 蟒蛇 3

```py
# Importing the library
import tensorflow as tf

# Initializing the Tensor
x = tf.Variable(3.0, name ="x")

with tf.GradientTape() as gfg:
  # y will evaluate to 9.0 i.e 3**2
  y = tf.grad_pass_through(x.assign)(x**2)

# res will evaluate to 6.0
res = gfg.gradient(y, x)

# Printing result
print("y: ", y)
print("res: ", res)
```

**输出:**

```py
y:  tf.Tensor(9.0, shape=(), dtype=float32)
res:  tf.Tensor(6.0, shape=(), dtype=float32)
```