# Python |使用 XlsxWriter 模块在 excel 表格中绘制折线图

> 原文:[https://www . geesforgeks . org/python-绘图-折线图-excel-sheet-use-xlsxwriter-module/](https://www.geeksforgeeks.org/python-plotting-line-charts-in-excel-sheet-using-xlsxwriter-module/)

**先决条件:** [在 excel 表格上创建并书写](https://www.geeksforgeeks.org/python-create-and-write-on-excel-file-using-xlsxwriter-module/)

**`XlsxWriter`** 是一个 Python 库，使用它可以对 excel 文件执行多种操作，如创建、编写、算术运算和绘制图形。让我们看看如何使用实时数据绘制折线图。

图表至少由一系列一个或多个数据点组成。系列本身由单元格区域的引用组成。要在 excel 表上绘制图表，首先要创建特定图表类型的图表对象(如折线图等)。).创建图表对象后，在其中插入数据，最后，将该图表对象添加到工作表对象中。

**代码:**绘制折线图。

在 excel 工作表中绘制`Line chart`时，使用带有工作簿对象类型`‘line’`关键字参数的 **`add_chart()`** 方法。

```
# import xlsxwriter module 
import xlsxwriter 

# Workbook() takes one, non-optional, argument   
# which is the filename that we want to create. 
workbook = xlsxwriter.Workbook('chart_Line.xlsx') 

# The workbook object is then used to add new   
# worksheet via the add_worksheet() method.  
worksheet = workbook.add_worksheet() 

# Create a new Format object to formats cells 
# in worksheets using add_format() method . 

# here we create bold format object . 
bold = workbook.add_format({'bold': 1}) 

# create a data list . 
headings = ['Number', 'Batch 1', 'Batch 2'] 

data = [ 
    [2, 3, 4, 5, 6, 7], 
    [80, 80, 100, 60, 50, 100], 
    [60, 50, 60, 20, 10, 20], 
] 

# Write a row of data starting from 'A1' 
# with bold format . 
worksheet.write_row('A1', headings, bold) 

# Write a column of data starting from  
# 'A2', 'B2', 'C2' respectively . 
worksheet.write_column('A2', data[0]) 
worksheet.write_column('B2', data[1]) 
worksheet.write_column('C2', data[2]) 

# Create a chart object that can be added 
# to a worksheet using add_chart() method. 

# here we create a line chart object . 
chart1 = workbook.add_chart({'type': 'line'}) 

# Add a data series to a chart 
# using add_series method. 

# Configure the first series. 
# = Sheet1 !$A$1 is equivalent to ['Sheet1', 0, 0].

# note : spaces is not inserted in b / w
# = and Sheet1, Sheet1 and !
# if space is inserted it throws warning.
chart1.add_series({ 
    'name':       '= Sheet1 !$B$1', 
    'categories': '= Sheet1 !$A$2:$A$7', 
    'values':     '= Sheet1 !$B$2:$B$7', 
}) 

# Configure a second series. 
# Note use of alternative syntax to define ranges. 
# [sheetname, first_row, first_col, last_row, last_col]. 
chart1.add_series({ 
    'name':       ['Sheet1', 0, 2], 
    'categories': ['Sheet1', 1, 0, 6, 0], 
    'values':     ['Sheet1', 1, 2, 6, 2], 
}) 

# Add a chart title  
chart1.set_title ({'name': 'Results of data analysis'}) 

# Add x-axis label 
chart1.set_x_axis({'name': 'Test number'}) 

# Add y-axis label 
chart1.set_y_axis({'name': 'Data length (mm)'}) 

# Set an Excel chart style. 
chart1.set_style(11) 

# add chart to the worksheet with given
# offset values at the top-left corner of
# a chart is anchored to cell D2 .  
worksheet.insert_chart('D2', chart1, {'x_offset': 25, 'y_offset': 10}) 

# Finally, close the Excel file  
# via the close() method.  
workbook.close() 
```

**输出:**
![Output-1](img/57bc7757e0f25d207176bcca90ea5ac0.png)