# 使用 Python 写入 excel 表格

> 原文:[https://www . geesforgeks . org/writing-excel-sheet-use-python/](https://www.geeksforgeeks.org/writing-excel-sheet-using-python/)

使用 **`xlwt`模块**，可以对电子表格进行多项操作。例如，可以用 Python 编写或修改数据。此外，用户可能需要浏览各种表单，根据某些标准检索数据，或者修改一些行和列，并做大量工作。

让我们看看如何使用 Python 创建和写入 excel 工作表。

**Code #1 :**

```py
# Writing to an excel 
# sheet using Python
import xlwt
from xlwt import Workbook

# Workbook is created
wb = Workbook()

# add_sheet is used to create sheet.
sheet1 = wb.add_sheet('Sheet 1')

sheet1.write(1, 0, 'ISBT DEHRADUN')
sheet1.write(2, 0, 'SHASTRADHARA')
sheet1.write(3, 0, 'CLEMEN TOWN')
sheet1.write(4, 0, 'RAJPUR ROAD')
sheet1.write(5, 0, 'CLOCK TOWER')
sheet1.write(0, 1, 'ISBT DEHRADUN')
sheet1.write(0, 2, 'SHASTRADHARA')
sheet1.write(0, 3, 'CLEMEN TOWN')
sheet1.write(0, 4, 'RAJPUR ROAD')
sheet1.write(0, 5, 'CLOCK TOWER')

wb.save('xlwt example.xls')
```