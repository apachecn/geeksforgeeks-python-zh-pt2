# Python |从文本文件中打乱单词

> 原文:[https://www . geesforgeks . org/python-scramble-word-from-a-text-file/](https://www.geeksforgeeks.org/python-scramble-words-from-a-text-file/)

给定文本文件中的一些数据，任务是对文本进行加扰，并在单独的文本文件中输出。因此，我们需要编写一个 Python 程序来读取一个文本文件，对文件中的单词进行加扰，并将输出写入一个新的文本文件。

**需遵守的规则:**

*   Words less than or equal to 3 characters need not be scrambled.
*   The first and last characters are not scrambled, so *scrambling* can become *srbmnacilg* or *srbmnailcg* or [T6】 snmbraclig 【T7], that is, letters other than the first and last characters can be scrambled in any order.
*   The punctuation mark at the end of the word remains unchanged, that is, "surprise" can become "Spsirnirug", but not "Spsirn, irug".
*   The following punctuation marks are supported-comma question mark, period, semicolon and exclamation point.
*   Do this for a file, keeping the order of lines.

在执行程序时，它应该提示用户输入输入文件名，并生成一个带有加密文本的输出文件。应该通过在输入文件名后附加单词“已加扰”来命名输出文件。

**例:**

```
Input :  MyFile.txt ->

Scrambling words is very  
interesting. Because even  
if they are scrambled, it   
doesn't impact our   
reading. Because we don't 
read letter by letter, we 
read the word as a whole.   

Output : MyFileScrambled.txt ->

Srbmnacilg words is very   
itrensientg. Bscauee even  
if tehy are srelabcmd, it  
dosn'et ipcmat our 
raidneg. Bacusee we dn'ot 
raed lteetr by letetr, we 
raed the word as a wolhe.
```

下面是实现:

## 蟒 3

```
import random

punct = (".", ";", "!", "?", ",")
count = 0
new_word = ""

inputfile = input("Enter input file name:")

with open(inputfile, 'r') as fin:
    for line in fin.readlines():  # Read line by line in txt file

        for word in line.split():  # Read word by word in each line

            if len(word) > 3:  # If word length >3

                '''If word ends with punctuation
                      Remove firstletter, lastletter and punctuation
                      Shuffle the words
                      Add the removed letters (first letter)
                      Add the removed letters (last letter)
                      Add the removed letters (punctuation mark)'''

                if word.endswith(punct):
                    word1 = word[1:-2]
                    word1 = random.sample(word1, len(word1))
                    word1.insert(0, word[0])
                    word1.append(word[-2])
                    word1.append(word[-1])

                    '''If there is no punctuation mark 
                      Remove first letter and last letter
                      Shuffle the word
                      Add the removed letters (first letter)
                      Add the removed letters (last letter)
                      Append the word and " " to the previous words'''

                else:
                    word1 = word[1:-1]
                    word1 = random.sample(word1, len(word1))
                    word1.insert(0, word[0])
                    word1.append(word[-1])
                    new_word = new_word + ''.join(word1) + " "

            '''If word length <3
                  just append the word and " " to the previous words'''

        else:
            new_word = new_word + word + " "

        # "Append to <filename>Scrambled.txt"

with open((inputfile[:-4] + "Scrambled.txt"), 'a+') as fout:
    fout.write(new_word + "\n")

new_word = ""
```

**输出:**

```
Smcinrablg wodrs very Bauscee eevn tehy dnoes't
icpamt Bcuesae d'not read lteter raed wrod whole. 
```