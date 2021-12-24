# Python |峰值信噪比(PSNR)

> 原文:[https://www . geesforgeks . org/python-峰值信噪比-psnr/](https://www.geeksforgeeks.org/python-peak-signal-to-noise-ratio-psnr/)

峰值信噪比(PSNR)是图像的最大可能功率和影响图像质量的破坏噪声功率之间的比值。为了估计图像的 PSNR，有必要将该图像与具有最大可能功率的理想干净图像进行比较。

**PSNR** 定义如下:

![ \[PSNR = 10log_{10}(\frac{(L - 1)^2}{MSE})= 20log_{10}(\frac{L - 1}{RMSE})\] ](img/cee565a97a2e5c41fe91127dbd8b40ff.png "Rendered by QuickLaTeX.com")

这里， **L** 是图像中最大可能强度等级(最小强度等级假设为 0)的数量。

**均方误差**是均方误差&它被定义为:

![ \[MSE = \frac{1}{mn}\sum_{i=0}^{m-1}\sum_{j=0}^{n-1}\left ( O(i, j) - D(i, j)\right )^{2}\] ](img/5681e193c417a872598ded71590d5ce9.png "Rendered by QuickLaTeX.com")

其中， **O** 表示原始图像的矩阵数据。 **D** 代表退化图像的矩阵数据。 **m** 代表像素的行数， **i** 代表图像的该行的索引。 **n** 表示像素的列数， **j** 表示图像的该列的索引。
**RMSE** 是均方根误差。

这里，我们有一个原始图像和它的压缩版本，让我们看看这些图像的 **PSNR** 值，

**原始图像:**
![](img/4a3dee045aecc8b1db02ac74989364fd.png)
**压缩图像:**
![](img/e9e71f3ac90f3cdf0c230c5a13152300.png)

下面是 Python 实现–

```
from math import log10, sqrt
import cv2
import numpy as np

def PSNR(original, compressed):
    mse = np.mean((original - compressed) ** 2)
    if(mse == 0):  # MSE is zero means no noise is present in the signal .
                  # Therefore PSNR have no importance.
        return 100
    max_pixel = 255.0
    psnr = 20 * log10(max_pixel / sqrt(mse))
    return psnr

def main():
     original = cv2.imread("original_image.png")
     compressed = cv2.imread("compressed_image.png", 1)
     value = PSNR(original, compressed)
     print(f"PSNR value is {value} dB")

if __name__ == "__main__":
    main()
```

**输出:**

```
PSNR value is 43.862955653517126 dB 
```

PSNR 最常用于估算压缩机、过滤器等的效率。PSNR 值越大，相应的压缩或过滤方法越有效。