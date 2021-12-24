# 均匀分布长周期线性

> 原文:[https://www . geesforgeks . org/well-equipment-long-period-linear/](https://www.geeksforgeeks.org/well-equidistributed-long-period-linear/)

**均匀分布长周期线性(WELL)** 是基于**线性反馈移位寄存器**技术产生伪随机数的伪随机数发生器算法。属于**线性同余发生器**家族。就功能而言，它类似于梅森扭扭器，因为它们都使用异或、移位和线性反馈移位机制工作。两者都需要一个种子值来启动生成过程。

伪随机数发生器是指一类算法，它利用一组初始种子值，并应用各种逻辑操作或移位操作来产生一个看似随机的数字。生成器可以递归定义如下:

```py
Xn+1 = (a*(Xn) + c) modulo-m

where X is a sequence of pseudorandom values, 
m is the modulus (m>0), 
a is the multiplier (0<a<m), 
c is the increment ( 0<c<m), 
and X0 is the seed ( 0<X0<m)

```

算法如下:

```py
0\.  Initialize the necessary seed values
1\.  Utilize a state array of a defined length (here it is 32)
2\.  Apply the necessary xor, shift and logical and operations to arrive at
    the required parameters
3a. Update the current location value and output that value from an array 
    location multiplied with a scaling constant
3b. newV0 and newV1 are additional pseudorandom numbers that can be supplied
    as per requirement

```

WELL 算法可以在短时间内产生多个数字，对于需要多个数字的应用非常有利。WELL 的一个主要缺点是状态空间较小。这可以通过利用更大尺寸的状态空间来改变，同时交换辅助空间。

**Python 代码实现–**

```py
# W stands for size of the digest, R is the size of the state
W = 32;R = 32 
# Variables used for jumping to a particular state
M1 = 3;M2 = 24;M3 = 10 

# can be changed to scale accordingly
FACT = 1.718 

# value based right shift with xor operation
def mat0pos(t, v):
    return(v^(v>>t))

# value based negative left shift with xor operation
def mat0neg(t, v):
    return(v^(v<<(~t)))

# returns the value itself (identity function)
def identity(v):
    return v

state = [None]*R

state_i = 0; z0 = None;z1 = None;z2 = None; newV1 = None; newV0 = None

# used to initialize the state of our digest based on argument provided
def InitWellRNG(arg):
    global state
    for j in range(0, len(arg)):
        state[j]= arg[j]

# function that utilizes seed values and logical operations to 
# output random numbers
def WELLRNG():
    global state_i
    global z0; global z1; global z2; global newV1; global newV0

    z0 = state[(state_i + M1) & 0x001f]
    z1 = identity(state[state_i]) ^ mat0pos(8, state[(state_i + M1) & 0x001f])
    z2 = mat0neg(-19, state[(state_i + M2) & 0x001f]) ^ mat0neg(-14,
                state[(state_i + M3) & 0x001f])

    # newV1 and newV0 are additional random values that are produced
    # and can be returned as per requirement
    newV1 = z1 ^ z2;
    newV0 = mat0neg(-11, z0) ^ mat0neg(-7, z1) ^ mat0neg(-13, z2)

    state_i = (state_i + (W-1)) & 0x001f
    return (state[state_i] *FACT)

# executed if this is the main file
if (__name__ == "__main__"):
    print("WELL created\n")
    # replace seed array with your own array to create different output
    # sequence of random numbers
    seed = [27, 10, 14, 27, 24, 4, 11, 25, 14, 13, 2, 20, 0, 22, 9, 24, 14, 9,
            20, 14, 17, 6, 21, 10, 27, 8, 16, 5, 26, 21, 18, 29]
    InitWellRNG(seed)
    for i in range(0,5):    
        print("random number generated is {}".format(WELLRNG()))

```

**输出:**

```py
WELL created

random number generated is 49.822
random number generated is 30.924
random number generated is 36.078
random number generated is 44.668
random number generated is 8.59

```