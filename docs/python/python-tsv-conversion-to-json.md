# Python–TSV 到 JSON 的转换

> 原文:[https://www . geesforgeks . org/python-tsv-conversion-to-JSON/](https://www.geeksforgeeks.org/python-tsv-conversion-to-json/)

在本文中，我们将讨论如何使用 Python 将 TSV 文件转换为 JSON。

## 将 TSV 转换为 JSON

这里出于演示的目的，我们将使用存储在 tsv 文件中的随机花卉数据集，表很少。

![](img/995bf83e55f3e7ae2f1e63e071669e7c.png)

花卉数据集

## 蟒蛇 3

```py
import json

def tsv2json(input_file,output_file):
    arr = []
    file = open(input_file, 'r')
    a = file.readline()

    # The first line consist of headings of the record 
    # so we will store it in an array and move to 
    # next line in input_file.
    titles = [t.strip() for t in a.split('\t')]
    for line in file:
        d = {}
        for t, f in zip(titles, line.split('\t')):

              # Convert each row into dictionary with keys as titles
            d[t] = f.strip()

        # we will use strip to remove '\n'.
        arr.append(d)

        # we will append all the individual dictionaires into list 
        # and dump into file.
    with open(output_file, 'w', encoding='utf-8') as output_file:
        output_file.write(json.dumps(arr, indent=4))

# Driver Code
input_filename = 'flower.tsv'
output_filename = 'flower.json'
tsv2json(input_filename,output_filename)
```