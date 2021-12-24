# Python 程序将 POS 转换为 SOP

> 原文:[https://www . geesforgeks . org/python-program-to-convert-pos-to-sop/](https://www.geeksforgeeks.org/python-program-to-convert-pos-to-sop/)

用 Python 编写一个程序，将标准 POS(和的乘积)形式转换为标准 SOP(和的乘积)形式。

**假设:**输入的 POS 表达式为标准。POS 表达式中的变量是连续的，即如果表达式包含变量 *A* ，那么它将分别有变量 *B* 、 *C* ，每个 Sum 项包含按排序顺序排列的字母，即 *A + B + C* (不像 B+A+C)。

**示例:**

```py
 Input : (A + B + C).(A + B + C').(A + B' + C).(A' + B + C)
Output : A'BC + AB'C + ABC' + ABC

Input : (A + B).(A' + B')
Output : A'B + AB'

```

**进场:**

1.  首先把每个和项转换成它的等价二进制形式。例如，如果(A+B+C′)，则取 0 表示非复合变量(A，B)，取 1 表示补码变量(C)，因此二进制转换为 011)，然后最终等效为其十进制形式(例如:001 = 1)，并存储在列表中。
2.  现在，对于标准操作程序表格，取第一步中形成的列表中没有的所有术语，然后将每个术语转换为二进制，并因此更改为位置表格。例如–
    假设 4 不在列表中，那么 5== > 101(二进制)
    现在，用补码变量(B)
    替换 0，用非复合变量(A，C)替换 1
    101 = =>AB’C
    在每个单独的和项之后使用“+”
    ex:AB’C+AB’C”

下面是上述方法的 Python 实现:

```py
# Python code to convert standard POS form 
# to standard SOP form 

# Function to calculate no. of variables 
# used in POS expression 
def count_no_alphabets(POS): 
    i = 0
    no_var = 0

    # As expression is standard so total no. 
    # of alphabets will be equal 
    # to alphabets before first '.' character 
    while (POS[i]!='.'): 

        # checking if character is alphabet         
        if (POS[i].isalpha()):     
            no_var+= 1
        i+= 1
    return no_var 

# Function to calculate the max terms in integers 
def Cal_Max_terms(Max_terms, POS): 
    a = "" 
    i = 0
    while (i<len(POS)): 
        if (POS[i]=='.'): 

            # converting binary to decimal                 
            b = int(a, 2) 

            # insertion of each min term(integer) into the list                 
            Max_terms.append(b) 

            # empty the string         
            a =""                         
            i+= 1

        elif(POS[i].isalpha()): 

            # checking whether variable is complemented or not 
            if(i + 1 != len(POS) and POS[i + 1]=="'"): 

                # concatenating the string with '0' 
                a += '1' 

                # incrementing by 2 because 1 for alphabet and 
                # another for "'"                        
                i += 2                            
            else: 

                # concatenating the string with '1' 
                a += '0'                        
                i += 1
        else: 
            i+= 1

    # insertion of last min term(integer) into the list     
    Max_terms.append(int(a, 2))         

# Function to calculate the min terms in binary then 
# calculate SOP form of POS 
def Cal_Min_terms(Max_terms, no_var, start_alphabet): 

    # declaration of the list 
    Min_terms =[] 

    # calculation of total no. of terms that can be 
    # formed by no_var variables                 
    max = 2**no_var                 
    for i in range(0, max): 

        # checking whether the term is not 
        # present in the max terms 
        if (Max_terms.count(i)== 0): 

            # converting integer to binary and then 
            # taking the value from 2nd index as 1st 
            # two index contains '0b' 
            b = bin(i)[2:] 

            # loop used for inserting 0's before the 
            # binary value so that its length will be 
            # equal to no. of variables present in 
            # each product term         
            while(len(b)!= no_var): 
                b ='0'+b 

            # appending the max terms(integer) in the list 
            Min_terms.append(b)     

    SOP = "" 

    # loop till there are min terms                         
    for i in Min_terms: 

        # acquire the starting variable came from 
        # main function in every product term             
        value = start_alphabet 

        # loop till there are 0's or 1's in each min term     
        for j in i: 

            # checking for complement variable to be used                 
            if (j =='0'): 

                # concatenating value, ' and + in string POS                 
                SOP = SOP + value+"'"

            # checking for uncomplement variable to be used     
            else: 

                # concatenating value and + in string POS                     
                SOP = SOP + value 

            # increment the alphabet by 1     
            value = chr(ord(value)+1) 

        # appending the SOP string by '+" after 
        # every product term                 
        SOP = SOP+ "+"

    # for discarding the extra '+' in the last                 
    SOP = SOP[:-1]                         
    return SOP 

# main function 
def main(): 

    # input1 
    POS_expr ="(A+B+C).(A+B+C').(A+B'+C).(A'+B + C)"
    Max_terms = [] 

    no_var = count_no_alphabets(POS_expr) 
    Cal_Max_terms(Max_terms, POS_expr) 
    SOP_expr = Cal_Min_terms(Max_terms, no_var, POS_expr[1]) 

    print("Standard SOP form of " + POS_expr + " ==> " + SOP_expr) 

    # input2 
    POS_expr ="(A + B).(A'+B')"
    Max_terms = [] 

    no_var = count_no_alphabets(POS_expr) 
    Cal_Max_terms(Max_terms, POS_expr) 
    SOP_expr = Cal_Min_terms(Max_terms, no_var, POS_expr[1]) 

    print ("Standard SOP form of " + POS_expr + " ==> " + SOP_expr) 

# Driver code 
if __name__=="__main__": 
    main() 
```

**Output:**

```py
Standard SOP form of (A+B+C).(A+B+C').(A+B'+C).(A'+B + C)  ==>  A'BC+AB'C+ABC'+ABC
Standard SOP form of (A + B).(A'+B')  ==>  A'B+AB'
```