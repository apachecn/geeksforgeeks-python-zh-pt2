# 使用 Python 的 RSA 数字签名方案

> 原文:[https://www . geesforgeks . org/RSA-数字签名-方案-使用-python/](https://www.geeksforgeeks.org/rsa-digital-signature-scheme-using-python/)

RSA 算法是一种非对称密码算法。非对称实际上意味着它使用两种不同的密钥，即公钥和私钥。顾名思义，公钥是给每个人的，私钥是保密的。

**非对称加密的一个例子:**

*   客户端(例如浏览器)将其公钥发送给服务器并请求一些数据。
*   服务器使用客户端的公钥加密数据，并发送加密的数据。
*   客户端接收并解密这些数据。

由于这是不对称的，除了浏览器之外，没有其他人可以解密数据，即使第三方拥有浏览器的公钥。
数字签名用于验证以电子方式发送的消息的真实性。数字签名算法使用公钥系统。预期的发送者用他/她的私钥签署他/她的消息，预期的接收者用发送者的公钥验证它。数字签名可以提供消息认证、消息完整性和不可否认性服务。

### 算法

**RSA 密钥生成:**

*   选择两个大质数 p 和 q
*   计算 n=p*q
*   选择公钥 e，使其不是(p-1)*(q-1)的因子
*   选择私钥 d，使得以下等式为真(d*e)mod(p-1)(q-1)=1 或 d 是模(p-1)*(q-1)中 E 的倒数

**RSA 数字签名方案:**在 RSA 中，d 是私有的；e 和 n 是公共的。

*   Alice 使用 S=M^d 模 n 创建她的数字签名，其中 m 是消息
*   爱丽丝向鲍勃发送信息 M 和签名 S
*   鲍勃计算 M1=S^e 模 n
*   如果 M1=M，那么鲍勃接受爱丽丝发送的数据。

下面是实现。

## 蟒蛇 3

```
# Function to find gcd
# of two numbers
def euclid(m, n):

    if n == 0:
        return m
    else:
        r = m % n
        return euclid(n, r)

# Program to find
# Multiplicative inverse
def exteuclid(a, b):

    r1 = a
    r2 = b
    s1 = int(1)
    s2 = int(0)
    t1 = int(0)
    t2 = int(1)

    while r2 > 0:

        q = r1//r2
        r = r1-q * r2
        r1 = r2
        r2 = r
        s = s1-q * s2
        s1 = s2
        s2 = s
        t = t1-q * t2
        t1 = t2
        t2 = t

    if t1 < 0:
        t1 = t1 % a

    return (r1, t1)

# Enter two large prime
# numbers p and q
p = 823
q = 953
n = p * q
Pn = (p-1)*(q-1)

# Generate encryption key
# in range 1<e<Pn
key = []

for i in range(2, Pn):

    gcd = euclid(Pn, i)

    if gcd == 1:
        key.append(i)

# Select an encryption key
# from the above list
e = int(313)

# Obtain inverse of
# encryption key in Z_Pn
r, d = exteuclid(Pn, e)
if r == 1:
    d = int(d)
    print("decryption key is: ", d)

else:
    print("Multiplicative inverse for\
    the given encryption key does not \
    exist. Choose a different encryption key ")

# Enter the message to be sent
M = 19070

# Signature is created by Alice
S = (M**d) % n

# Alice sends M and S both to Bob
# Bob generates message M1 using the
# signature S, Alice's public key e
# and product n.
M1 = (S**e) % n

# If M = M1 only then Bob accepts
# the message sent by Alice.

if M == M1:
    print("As M = M1, Accept the\
    message sent by Alice")
else:
    print("As M not equal to M1,\
    Do not accept the message\
    sent by Alice ")
```

**输出:**

```
decryption key is:  160009
As M = M1, Accept the message sent by Alice
```