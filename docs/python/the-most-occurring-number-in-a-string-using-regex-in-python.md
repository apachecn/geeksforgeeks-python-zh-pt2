# 在 python 中使用 Regex 的字符串中出现次数最多的数字

> 原文:[https://www . geeksforgeeks . org/出现次数最多的字符串中数字使用-regex-in-python/](https://www.geeksforgeeks.org/the-most-occurring-number-in-a-string-using-regex-in-python/)

给定一个字符串 **str** ，任务是从一个字符串中提取所有的数字，并使用 Regex Python 找出其中出现最多的元素。

*   It is guaranteed that no two element have the same frequency
    **Examples:**

    ```py
    Input :geek55of55geeks4abc3dr2 
    Output :55

    Input :abcd1def2high2bnasvd3vjhd44
    Output :2

    ```

    **方法:**使用 python 中 regex 库的 **re.findall()** 函数从一个字符串 **str** 中提取所有数字，使用集合库中的 **Counter** 函数可以得到出现次数最多的元素。

    下面是上述方法的 Python 实现

    ```py
    # your code goes here# Python program to 
    # find the most occurring element 
    import re 
    from collections import Counter 

    def most_occr_element(word):

        # re.findall will extract all the elements 
        # from the string and make a list
        arr = re.findall(r'[0-9]+', word)    

        # to store maxm frequency
        maxm = 0  

        # to store maxm element of most frequency
        max_elem = 0

        # counter will store all the number with 
        # their frequencies
        # c = counter((55, 2), (2, 1), (3, 1), (4, 1))    
        c = Counter(arr)

        # Store all the keys of counter in a list in
        # which first would we our required element    
        for x in list(c.keys()):

            if c[x]>= maxm:
                maxm = c[x]
                max_elem = int(x)

        return max_elem

    # Driver program 
    if __name__ == "__main__": 
        word = 'geek55of55gee4ksabc3dr2x'
        print(most_occr_element(word))
    ```

    **Output:**

    ```py
    55

    ```