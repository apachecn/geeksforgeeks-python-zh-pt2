# Python |使用 XlsxWriter 模块绘制带有渐变填充的 Excel 图表

> 原文:[https://www . geesforgeks . org/python-绘图-带渐变填充的 excel 图表-使用-xlsxwriter-module/](https://www.geeksforgeeks.org/python-plotting-an-excel-chart-with-gradient-fills-using-xlsxwriter-module/)

**先决条件:** [在 excel 表格上创建并书写](https://www.geeksforgeeks.org/python-create-and-write-on-excel-file-using-xlsxwriter-module/)

**`XlsxWriter`** 是一个 Python 库，使用它可以对 excel 文件执行多种操作，如创建、编写、算术运算和绘制图形。让我们看看如何使用实时数据绘制带有渐变填充的图表。

图表至少由一系列一个或多个数据点组成。系列本身由单元格区域的引用组成。要在 excel 表上绘制图表，首先要创建特定图表类型的图表对象(如柱形图等)。).创建图表对象后，在其中插入数据，最后，将该图表对象添加到工作表对象中。

**代码#1 :** 绘制带渐变填充列的图表。
要在 excel 表上绘制这种类型的图表，请使用带有图表对象的`'gradient'`关键字参数的`add_series()`方法。

```
# import xlsxwriter module
import xlsxwriter

# Workbook() takes one, non-optional, argument   
# which is the filename that we want to create.
workbook = xlsxwriter.Workbook('chart_gradient1.xlsx')

# The workbook object is then used to add new   
# worksheet via the add_worksheet() method.
worksheet = workbook.add_worksheet()

# Create a new Format object to formats cells 
# in worksheets using add_format() method . 

# here we create bold format object . 
bold = workbook.add_format({'bold': 1})

# Add the worksheet data that the charts will refer to.
headings = ['Number', 'Batch 1', 'Batch 2']
data = [
    [2, 3, 4, 5, 6, 7],
    [10, 40, 50, 20, 10, 50],
    [30, 60, 70, 50, 40, 30],
]

# Write a row of data starting from 'A1' 
# with bold format 
worksheet.write_row('A1', headings, bold)

# Write a column of data starting from  
# 'A2', 'B2', 'C2' respectively . 
worksheet.write_column('A2', data[0])
worksheet.write_column('B2', data[1])
worksheet.write_column('C2', data[2])

# Create a chart object that can be added 
# to a worksheet using add_chart() method. 

# here we create a column chart object 
chart = workbook.add_chart({'type': 'column'})

# Add a data series with Gradient to a chart 
# using add_series method.

# Configure the first series . 
# = Sheet1 !$A$1 is equivalent to ['Sheet1', 0, 0].

# note : spaces is not inserted in b / w
# = and Sheet1, Sheet1 and !
# if space is inserted it throws warning.
chart.add_series({
    'name':       '= Sheet1 !$B$1',
    'categories': '= Sheet1 !$A$2:$A$7',
    'values':     '= Sheet1 !$B$2:$B$7',
    'gradient':   {'colors': ['# 963735', '# F1DCDB']}
})

# Configure the second series, including a gradient.
chart.add_series({
    'name':       '= Sheet1 !$C$1',
    'categories': '= Sheet1 !$A$2:$A$7',
    'values':     '= Sheet1 !$C$2:$C$7',
    'gradient':   {'colors': ['# E36C0A', '# FCEADA']}
})

# Add a chart title 
chart.set_title ({'name': 'Chart With Gradient Fills'})

# Add x-axis label 
chart.set_x_axis({'name': 'Test number'})

# Add y-axis label
chart.set_y_axis({'name': 'Sample length (mm)'})

# Turn off the chart legend.
chart.set_legend({'none': True})

# add chart to the worksheet with given
# offset values at the top-left corner of
# a chart is anchored to cell D2 .
worksheet.insert_chart('D2', chart,
  {'x_offset': 25, 'y_offset': 10})

# Finally, close the Excel file  
# via the close() method.  
workbook.close()
```

**输出:**
![output1](img/3222f27b875732b0d4f8ac08547a0b0e.png)

**代码#2 :** 在绘图区域绘制带有渐变填充的图表。
在 excel 表上绘制这种类型的图表时，使用带有图表对象的`'gradient'`关键字参数的`set_plotarea()`方法。

```
# import xlsxwriter module
import xlsxwriter

# Workbook() takes one, non-optional, argument   
# which is the filename that we want to create.
workbook = xlsxwriter.Workbook('chart_gradient2.xlsx')

# The workbook object is then used to add new   
# worksheet via the add_worksheet() method.
worksheet = workbook.add_worksheet()

# Create a new Format object to formats cells 
# in worksheets using add_format() method . 

# here we create bold format object . 
bold = workbook.add_format({'bold': 1})

# Add the worksheet data that the charts will refer to.
headings = ['Number', 'Batch 1', 'Batch 2']
data = [
    [2, 3, 4, 5, 6, 7],
    [10, 40, 50, 20, 10, 50],
    [30, 60, 70, 50, 40, 30],]

# Write a row of data starting from 'A1' 
# with bold format 
worksheet.write_row('A1', headings, bold)

# Write a column of data starting from  
# 'A2', 'B2', 'C2' respectively . 
worksheet.write_column('A2', data[0])
worksheet.write_column('B2', data[1])
worksheet.write_column('C2', data[2])

# Create a chart object that can be added 
# to a worksheet using add_chart() method. 

# here we create a column chart object 
chart = workbook.add_chart({'type': 'column'})

# Add a data series to a chart 
# using add_series method.

# Configure the first series . 
# = Sheet1 !$A$1 is equivalent to ['Sheet1', 0, 0].

# note : spaces is not inserted in b / w
# = and Sheet1, Sheet1 and !
# if space is inserted it throws warning.
chart.add_series({
    'name':       '= Sheet1 !$B$1',
    'categories': '= Sheet1 !$A$2:$A$7',
    'values':     '= Sheet1 !$B$2:$B$7',})

# Configure the second series.
chart.add_series({
    'name':       '= Sheet1 !$C$1',
    'categories': '= Sheet1 !$A$2:$A$7',
    'values':     '= Sheet1 !$C$2:$C$7',})

# Set a gradient for the plotarea.
chart.set_plotarea({
    'gradient': {'colors': ['# FFEFD1', '# F0EBD5', '# B69F66']}
})

# Add a chart title 
chart.set_title ({'name': 'Chart With Gradient Fills on Plot Area'})

# Add x-axis label 
chart.set_x_axis({'name': 'Test number'})

# Add y-axis label
chart.set_y_axis({'name': 'Sample length (mm)'})

# Turn off the chart legend.
chart.set_legend({'none': True})

# add chart to the worksheet with given
# offset values at the top-left corner of
# a chart is anchored to cell D2 .
worksheet.insert_chart('D2', chart,
   {'x_offset': 25, 'y_offset': 10})

# Finally, close the Excel file  
# via the close() method.  
workbook.close()
```

**输出:**
![output2](img/8b8ec6f8e8465572c4ae6b2218ac119f.png)