# Python |使用 XlsxWriter 模块在 excel 工作表中绘制组合图表

> 原文:[https://www . geesforgeks . org/python-绘图-组合-excel 中的图表-工作表-使用-xlsxwriter-module/](https://www.geeksforgeeks.org/python-plotting-combined-charts-in-excel-sheet-using-xlsxwriter-module/)

**先决条件:** [在 excel 表格上创建和书写](https://www.geeksforgeeks.org/python-create-and-write-on-excel-file-using-xlsxwriter-module/)
**XlsxWriter** 是一个 Python 库，使用它可以对 excel 文件执行多种操作，如创建、书写、算术运算和绘制图形。让我们看看如何使用实时数据绘制组合图表。
图表由至少一系列一个或多个数据点组成。系列本身由单元格区域的引用组成。要在 excel 表上绘制图表，首先要创建特定图表类型的图表对象(如折线图、柱形图等)。).创建图表对象后，在其中插入数据，最后，将该图表对象添加到工作表对象中。

**代码#1 :** 绘制共享相同 X 轴和 Y 轴的组合柱形图和折线图。
要在 excel 工作表中绘制组合图表，请使用图表对象的 combine()方法将两个图表对象组合在一起。

## 蟒蛇 3

```py
# import xlsxwriter module
import xlsxwriter

# Workbook() takes one, non-optional, argument  
# which is the filename that we want to create.
workbook = xlsxwriter.Workbook('chart_combined.xlsx')

# The workbook object is then used to add new  
# worksheet via the add_worksheet() method.
worksheet = workbook.add_worksheet()

# Create a new Format object to formats cells
# in worksheets using add_format() method .

# here we create bold format object .
bold = workbook.add_format({'bold': True})

# Add the worksheet data that the charts will refer to.
headings = ['Number', 'Batch 1', 'Batch 2']
data = [
    [2, 3, 4, 5, 6, 7],
    [10, 40, 50, 20, 10, 50],
    [30, 60, 70, 50, 40, 30],
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

# here we create a column chart object .
# This will use as the primary chart.
column_chart1 = workbook.add_chart({'type': 'column'})

# Add a data series to a chart
# using add_series method.

# Configure the first series.
# = Sheet1 !$A$1 is equivalent to ['Sheet1', 0, 0].

# note : spaces is not inserted in b / w
# = and Sheet1, Sheet1 and !
# if space is inserted it throws warning.
column_chart1.add_series({
    'name':       '= Sheet1 !$B$1',
    'categories': '= Sheet1 !$A$2:$A$7',
    'values':     '= Sheet1 !$B$2:$B$7',
})

# Create a new line chart.
# This will use as the secondary chart.
line_chart1 = workbook.add_chart({'type': 'line'})

# Configure the data series for the secondary chart.
line_chart1.add_series({
    'name':       '= Sheet1 !$C$1',
    'categories': '= Sheet1 !$A$2:$A$7',
    'values':     '= Sheet1 !$C$2:$C$7',
})

# Combine both column and line charts together.
column_chart1.combine(line_chart1)

# Add a chart title 
column_chart1.set_title({ 'name': 'Combined chart - same Y axis'})

# Add x-axis label
column_chart1.set_x_axis({'name': 'Test number'})

# Add y-axis label
column_chart1.set_y_axis({'name': 'Sample length (mm)'})

# add chart to the worksheet with given
# offset values at the top-left corner of
# a chart is anchored to cell D2
worksheet.insert_chart('D2', column_chart1, {'x_offset': 25, 'y_offset': 10})

# Finally, close the Excel file 
# via the close() method. 
workbook.close()
```