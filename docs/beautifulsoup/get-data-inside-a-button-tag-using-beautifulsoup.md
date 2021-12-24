# 使用“美化组”

获取按钮标签内的数据

> 原文:[https://www . geeksforgeeks . org/get-data-inside-a-button-tag-using-beautulsoup/](https://www.geeksforgeeks.org/get-data-inside-a-button-tag-using-beautifulsoup/)

有时候，当使用美丽的程序时，你是否陷入了必须在按钮标签中获取数据的境地？别担心。只要读读这篇文章，就能知道你是如何做到的。

例如，考虑这个简单的页面源有一个按钮标签。

## HTML

```py
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Apple</title>
</head>
<body>
  <button id="enjoy" onclick="gfg.html">
      Click Me!
  </button>
</body>
</html>
```