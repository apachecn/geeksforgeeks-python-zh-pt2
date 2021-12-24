# 用 Python-Selenium 从网站上刮表

> 原文:[https://www . geeksforgeeks . org/从网站刮表-使用-python-selenium/](https://www.geeksforgeeks.org/scrape-table-from-website-using-python-selenium/)

**Selenium** 是获取网站，执行各种动作，或者从网站获取数据的自动化软件测试工具。它主要是为了通过自动化 web 应用程序来简化测试工作而开发的。如今，除了用于测试，它还可以用于使繁琐的工作变得有趣。你知道在 Selenium 的帮助下，你也可以从网站上的表格中提取数据吗？答案是**是的**，我们可以很容易地从网站上报废表格数据。这篇文章解释了从网站上抓取表格数据需要做什么。

### 应遵循的方法:

让我们考虑包含表格的简单 HTML 程序，仅仅是为了理解从网站上抓取表格的方法。

## HTML

```py
<!DOCTYPE html>
<html>
   <head>
      <title>Selenium Table</title>
   </head>
   <body>
      <table border="1">
        <thead>
         <tr>
            <th>Name</th>
            <th>Class</th>
         </tr>
        </thead>
        <tbody>
         <tr>
            <td>Vinayak</td>
            <td>12</td>
         </tr>
         <tr>
            <td>Ishita</td>
            <td>10</td>
         </tr>
        </tbody>
      </table>
   </body>
</html>
```