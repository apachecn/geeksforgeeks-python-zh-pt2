# Python |使用 XlsxWriter 模块在 excel 工作表中使用数据工具绘制图表| Set–1

> 原文:[https://www . geesforgeks . org/python-绘图-excel 中的图表-带数据的工作表-工具-使用-xlsxwriter-module-set-1/](https://www.geeksforgeeks.org/python-plotting-charts-in-excel-sheet-with-data-tools-using-xlsxwriter-module-set-1/)

**先决条件:** [在 excel 表格上创建和书写](https://www.geeksforgeeks.org/python-create-and-write-on-excel-file-using-xlsxwriter-module/)
**XlsxWriter** 是一个 Python 库，使用它可以对 excel 文件执行多种操作，如创建、书写、算术运算和绘制图形。让我们看看如何使用不同类型的数据工具使用实时数据绘制图表。

图表至少由一系列一个或多个数据点组成。系列本身由单元格区域的引用组成。要在 excel 表上绘制图表，首先要创建特定图表类型的图表对象(如折线图等)。).创建图表对象后，在其中插入数据，最后，将该图表对象添加到工作表对象中。

**代码#1 :** 用趋势线绘制图表。

要在 excel 工作表中绘制这种类型的图表，请将 add_series()方法与图表对象的“趋势线”关键字参数一起使用。

## 蟒蛇 3

```py
# import xlsxwriter module
import xlsxwriter

# Workbook() takes one, non-optional, argument  
# which is the filename that we want to create.
workbook = xlsxwriter.Workbook('Example1_chart.xlsx')

# The workbook object is then used to add new  
# worksheet via the add_worksheet() method.
worksheet = workbook.add_worksheet()

# Create a new Format object to formats cells
# in worksheets using add_format() method .

# here we create italic format object
italic = workbook.add_format({'italic': 1})

# Add the worksheet data that the charts will refer to.
Data1 = ['Subject', 'Mid Exam Score', 'End Exam Score']
Data2 = [
    ["Math", "Physics", "Computer", "Hindi", "English", "chemistry"],
    [90, 78, 60, 80, 60, 90],
    [45, 39, 30, 40, 30, 60]
]

# Write a row of data starting from 'A1'
# with bold format .
worksheet.write_row('A1', Data1, italic)

# Write a column of data starting from 
# 'A2', 'B2', 'C2' respectively
worksheet.write_column('A2', Data2[0])
worksheet.write_column('B2', Data2[1])
worksheet.write_column('C2', Data2[2])

# set the width of B and C column
worksheet.set_column('B:C', 15)

# Create a chart object that can be added
# to a worksheet using add_chart() method.

# here we create a line chart object .
chart1 = workbook.add_chart({'type': 'line'})

# Add a data series to a chart
# using add_series method.

# Configure the first series.
# with a polynomial trendline.
# = Sheet1 !$A$1 is equivalent to ['Sheet1', 0, 0].

# note : spaces is not inserted in b / w
# = and Sheet1, Sheet1 and !
# if space is inserted it throws warning.
chart1.add_series({
    'categories': '= Sheet1 !$A$2:$A$7',
    'values':     '= Sheet1 !$B$2:$B$7',
    'trendline': {
        'type': 'polynomial',
        'order': 2,
        'line': {
            'color': 'red',
            'width': 2,
            'dash_type': 'long_dash',
        },
    },
})

# Configure the second series with
# a moving average trendline.
chart1.add_series({
    'categories': '= Sheet1 !$A$2:$A$7',
    'values':     '= Sheet1 !$C$2:$C$7',
    'trendline': {'type': 'linear'},
    'line': {
            'color': 'red',
            'width': 1,
            },
})

# Add a chart title.
chart1.set_title({'name': 'Exam Score Distribution'})

# Add x-axis label
chart1.set_x_axis({'name': 'Subjects'})

# Add y-axis label
chart1.set_y_axis({'name': 'Marks'})

# Set an Excel chart style.
chart1.set_style(11)

# add chart to the worksheet with given
# offset values at the top-left corner of
# a chart is anchored to cell D2
worksheet.insert_chart('D2', chart1,
    {'x_offset': 20, 'y_offset': 5})

# Finally, close the Excel file 
# via the close() method. 
workbook.close()
```

**输出:**

![output-1](img/167a713493122b9341c84796e65a0dc7.png)

**代码#2 :** 绘制带有数据标签和标记的图表。

要在 excel 工作表中绘制这种类型的图表，请将 add_series()方法与图表对象的“data_labels”和“marker”关键字参数一起使用。

## 蟒蛇 3

```py
# import xlsxwriter module
import xlsxwriter

# Workbook() takes one, non-optional, argument  
# which is the filename that we want to create.
workbook = xlsxwriter.Workbook('Example2_chart.xlsx')

# The workbook object is then used to add new  
# worksheet via the add_worksheet() method.
worksheet = workbook.add_worksheet()

# Create a new Format object to formats cells
# in worksheets using add_format() method .

# here we create italic format object
italic = workbook.add_format({'italic': 1})

# Add the worksheet data that the charts will refer to.
Data1 = ['Subject', 'Mid Exam Score', 'End Exam Score']
Data2 = [
    ["Math", "Physics", "Computer", "Hindi", "English", "chemistry"],
    [90, 78, 60, 80, 60, 90],
    [45, 39, 30, 40, 30, 60]
]

# Write a row of data starting from 'A1'
# with bold format .
worksheet.write_row('A1', Data1, italic)

# Write a column of data starting from 
# 'A2', 'B2', 'C2' respectively
worksheet.write_column('A2', Data2[0])
worksheet.write_column('B2', Data2[1])
worksheet.write_column('C2', Data2[2])

# set the width of B and C column
worksheet.set_column('B:C', 15)

# Create a chart object that can be added
# to a worksheet using add_chart() method.

# here we create a line chart object .
chart2 = workbook.add_chart({'type': 'line'})

# Add a data series to a chart
# using add_series method.

# Configure the first series.
# with a data label and marker.
# = Sheet1 !$A$1 is equivalent to ['Sheet1', 0, 0].

# note : spaces is not inserted in b / w
# = and Sheet1, Sheet1 and !
# if space is inserted it throws warning.
chart2.add_series({
    'categories': '= Sheet1 !$A$2:$A$7',
    'values':     '= Sheet1 !$B$2:$B$7',
    'data_labels': {'value': 1},
    'marker': {'type': 'automatic'},
})

# Configure the second series with
# a moving average trendline.
chart2.add_series({
    'categories': '= Sheet1 !$A$2:$A$7',
    'values':     '= Sheet1 !$C$2:$C$7',
})

# Add a chart title.
chart2.set_title({'name': 'Exam Score Distribution'})

# Add x-axis label
chart2.set_x_axis({'name': 'Subjects'})

# Add y-axis label
chart2.set_y_axis({'name': 'Marks'})

# Set an Excel chart style.
chart2.set_style(11)

# add chart to the worksheet with given
# offset values at the top-left corner of
# a chart is anchored to cell D2
worksheet.insert_chart('D2', chart2,
     {'x_offset': 25, 'y_offset': 10})

# Finally, close the Excel file 
# via the close() method. 
workbook.close()
```

**输出:**

![output-2](img/9667710f63368493c85c2cb09a378d2a.png)

**代码#3 :** 绘制带有误差线的图表。

要在 excel 工作表中绘制这种类型的图表，请将 add_series()方法与图表对象的“y _ error _ bars”关键字参数一起使用。

## 蟒蛇 3

```py
# import xlsxwriter module
import xlsxwriter

# Workbook() takes one, non-optional, argument  
# which is the filename that we want to create.
workbook = xlsxwriter.Workbook('Example3_chart.xlsx')

# The workbook object is then used to add new  
# worksheet via the add_worksheet() method.
worksheet = workbook.add_worksheet()

# Create a new Format object to formats cells
# in worksheets using add_format() method .

# here we create italic format object
italic = workbook.add_format({'italic': 1})

# Add the worksheet data that the charts will refer to.
Data1 = ['Subject', 'Mid Exam Score', 'End Exam Score']
Data2 = [
    ["Math", "Physics", "Computer", "Hindi", "English", "chemistry"],
    [95, 78, 80, 80, 60, 90],
    [90, 50, 95, 60, 85, 99]
]

# Write a row of data starting from 'A1'
# with bold format .
worksheet.write_row('A1', Data1, italic)

# Write a column of data starting from 
# 'A2', 'B2', 'C2' respectively
worksheet.write_column('A2', Data2[0])
worksheet.write_column('B2', Data2[1])
worksheet.write_column('C2', Data2[2])

# set the width of B and C column
worksheet.set_column('B:C', 15)

# Create a chart object that can be added
# to a worksheet using add_chart() method.

# here we create a line chart object .
chart3 = workbook.add_chart({'type': 'line'})

# Add a data series to a chart
# using add_series method.

# Configure the first series.
# with a error bars .
# = Sheet1 !$A$1 is equivalent to ['Sheet1', 0, 0].

# note : spaces is not inserted in b / w
# = and Sheet1, Sheet1 and !
# if space is inserted it throws warning.
chart3.add_series({
    'categories': '= Sheet1 !$A$2:$A$7',
    'values':     '= Sheet1 !$B$2:$B$7',
    'y_error_bars': {'type': 'standard_error'},
})

# Configure the second series.
chart3.add_series({
    'categories': '= Sheet1 !$A$2:$A$7',
    'values': '= Sheet1 !$C$2:$C$7',
})

# Add a chart title.
chart3.set_title({'name': 'Exam Score Distribution'})

# Add x-axis label
chart3.set_x_axis({'name': 'Subjects'})

# Add y-axis label
chart3.set_y_axis({'name': 'Marks'})

# Set an Excel chart style.
chart3.set_style(14)

# add chart to the worksheet with given
# offset values at the top-left corner of
# a chart is anchored to cell D2
worksheet.insert_chart('D2', chart3,
    {'x_offset': 20, 'y_offset': 5})

# Finally, close the Excel file 
# via the close() method. 
workbook.close()
```

**输出:**

![output-3](img/1649af8f12f5bb77b333b7ff5d55b091.png)