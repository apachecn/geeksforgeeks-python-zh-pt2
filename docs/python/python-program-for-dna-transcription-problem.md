# 针对 DNA 转录问题的 Python 程序

> 原文:[https://www . geesforgeks . org/python-program-for-DNA-转录-问题/](https://www.geeksforgeeks.org/python-program-for-dna-transcription-problem/)

我们来讨论一下 Python 中的 DNA 转录问题。首先，让我们了解一下将在这个问题中使用的脱氧核糖核酸和核糖核酸的基础知识。

*   **在 DNA 中发现的四个核苷酸:**腺嘌呤(A)、胞嘧啶(C)、鸟嘌呤(G)和胸腺嘧啶(T)。
*   **RNA 中发现的四个核苷酸:**腺嘌呤(A)、胞嘧啶(C)、鸟嘌呤(G)和尿嘧啶(U)。

给定一条脱氧核糖核酸链，它的转录核糖核酸链是通过用它的互补核苷酸替换每个核苷酸而形成的:

*   g–> C
*   c–> G
*   t–> A
*   答–> U

**示例:**

```py
Input: GCTAA
Output: CGAUU

Input: GC
Output: CG 

```

**进场:**

将输入作为字符串，然后将其转换为字符列表。然后遍历列表中的每个字符。检查字符是“G”还是“C”或“T”还是“A”，然后分别将其转换为“C”、“G”、“A”和“U”。否则打印“无效输入”。

下面是实现:

## 蟒蛇 3

```py
# define a function
# for transcription
def transcript(x) :

  # convert string into list
  l = list(x)  

  for i in range(len(x)):

      if(l[i]=='G'):
          l[i]='C'

      elif(l[i]=='C'):
          l[i]='G'

      elif (l[i] == 'T'):
          l[i] = 'A'

      elif (l[i] == 'A'):
          l[i] = 'U'

      else:
          print('Invalid Input')                      

  print("Translated DNA : ",end="")      
  for char in l:
      print(char,end="")

# Driver code
if __name__ == "__main__":

  x = "GCTAA"
  # function calling
  transcript(x)
```

**输出:**

```py
Translated DNA : CGAUU

```