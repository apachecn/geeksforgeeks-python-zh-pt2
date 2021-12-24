# Python 程序替换文件中的文本

> 原文:[https://www . geesforgeks . org/python-程序替换文件中的文本/](https://www.geeksforgeeks.org/python-program-to-replace-text-in-a-file/)

在本文中，我们将使用 Python 替换文件中的文本。替换文本可能是擦除文件的全部内容并用新的文本替换，也可能意味着只修改现有文本中的特定单词或句子。

### **方法 1** :删除所有文本，在同一个文件中写入新文本

在这种方法中，我们替换存储在文本文件中的所有文本，为此，我们将以读写模式打开文件，它将重写所有文本。

## 蟒 3

```
# Python program to replace text in a file
s = input("Enter text to replace the existing contents:")
f = open("file.txt", "r+")

# file.txt is an example here,
# it should be replaced with the file name
# r+ mode opens the file in read and write mode
f.truncate(0)
f.write(s)
f.close()
print("Text successfully replaced")
```