# Python–tensorflow . math . is _ strict _ 递增()

> 原文:[https://www . geesforgeks . org/python-tesorflow-math-is _ strict _ 递增/](https://www.geeksforgeeks.org/python-tesorflow-math-is_strictly_increasing/)

TensorFlow 是谷歌设计的开源 Python 库，用于开发机器学习模型和深度学习神经网络。

**为 _ 严格递增()**如果 x 为严格递增，则返回 true。如果 x 的元素少于 2 个，那么它就是严格递增的。Row major 用于比较元素。

> **语法:**tensorflow . math . is _ strict _ 递增(x，name)
> 
> **参数:**
> 
> *   **x:** 是数值张量。
> *   **名称(可选):**定义操作的名称
> 
> **返回:**返回数据类型布尔的张量。

**例 1:**

## 蟒蛇 3

```
# importing the library
import tensorflow as tf

# Initializing the input tensor
a = tf.constant([2, 3, 3, 5], dtype = tf.float64)

# Printing the input tensor
print('a: ', a)

# Calculating the result
res = tf.math.is_strictly_increasing(a)

# Printing the result
print('Result: ', res)
```

**输出:**

```
a:  tf.Tensor([2\. 3\. 3\. 5.], shape=(4, ), dtype=float64)
Result:  tf.Tensor(False, shape=(), dtype=bool)
```

**例 2:**

## 蟒蛇 3

```
# Importing the library
import tensorflow as tf

# Initializing the input tensor
a = tf.constant([7, 8, 13, 17], dtype = tf.float64)

# Printing the input tensor
print('a: ', a)

# Calculating the result
res = tf.math.is_strictly_increasing(a)

# Printing the result
print('Result: ', res)
```

**输出:**

```
a:  tf.Tensor([ 7\.  8\. 13\. 17.], shape=(4, ), dtype=float64)
Result:  tf.Tensor(True, shape=(), dtype=bool)
```