# Python 中的智能计算器

> 原文:[https://www.geeksforgeeks.org/smart-calculator-in-python/](https://www.geeksforgeeks.org/smart-calculator-in-python/)

**问题**–这个智能计算器也适用于文本语句。用户不必总是提供代数表达式。它从命令(由用户给出)中提取单词，然后形成表达式。

**示例:**

```py
Input  : Hi calculator plz find the lcm of 4 and 8\.  
Output : 8 

Input  : Hi smart plz find the  multiplication of 3 and 9\. 
Output : 27 

Input  : Hi smart plz end the program. 
Output : Thanks for enjoy with me.

```

**代码:智能计算的 Python 代码**

```py
# main python proghram
response=['Welcome to smart calculator','My name is MONTY',
          'Thanks for enjoy with me ','Sorry ,this is  beyond my ability']

# fetching tokens from the text command
def extract_from_text(text):
    l=[]
    for t in text.split(' '):
        try:
            l.append(float(t))
        except ValueError:
            pass
    return l

# calculating LCM
def lcm(a,b):
    L=a if a>b else b
    while L<=a*b:
        if L%a==0 and L%b==0:
            return L
        L+=1

# calculating HCF
def hcf(a,b):
    H=a if a<b else b
    while H>=1:
        if a%H==0 and b%H==0:
            return H
        H-=1

# Addition
def add(a,b):
    return a+b

# Subtraction
def sub(a,b):
    return a-b

# Multiplication
def mul(a,b):
    return a*b

# Division
def div(a,b):
    return a/b

# Remainder
def mod(a,b):
    return a%b

# Response to command
# printing - "Thanks for enjoy with me" on exit
def end():
    print(response[2])
    input('press enter key to exit')
    exit()

def myname():
    print(response[1])
def sorry():
    print(response[3])

# Operations - performed on the basis of text tokens
operations={'ADD':add,'PLUS':add,'SUM':add,'ADDITION':add,
            'SUB':sub,'SUBTRACT':sub, 'MINUS':sub,
            'DIFFERENCE':sub,'LCM':lcm,'HCF':hcf,
            'PRODUCT':mul, 'MULTIPLY':mul,'MULTIPLICATION':mul,
            'DIVISION':div,'MOD':mod,'REMANDER'
            :mod,'MODULAS':mod}

# commands
commands={'NAME':myname,'EXIT':end,'END':end,'CLOSE':end}

print('--------------'+response[0]+'------------')
print('--------------'+response[1]+'--------------------')

while True:
    print()
    text=input('enter your queries:  ')
    for word in text.split(' '):
        if word.upper() in operations.keys():
            try:
                l = extract_from_text(text)
                r = operations[word.upper()] (l[0],l[1])
                print(r)
            except:
                print('something went wrong going plz enter again !!')
            finally:
                      break
        elif word.upper() in commands.keys():
                      commands[word.upper()]()
                      break
    else:         
        sorry()
```

**输出:**

```py
--------------Welcome to smart calculator------------
--------------My name is MONTY--------------------

enter your queries:  tell me the hcf of 4 and 8
4.0

enter your queries:  hi plz tell me 7 + 8
Sorry ,this is  beyond my ability

enter your queries:  pls add 7 and 8
15.0

```