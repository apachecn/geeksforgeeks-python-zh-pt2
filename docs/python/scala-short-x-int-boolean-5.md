# Scala short ==(x: Int):布尔值

> 原文:[https://www.geeksforgeeks.org/scala-short-x-int-boolean-5/](https://www.geeksforgeeks.org/scala-short-x-int-boolean-5/)

简言之，16 位有符号整数(相当于 Java 的短原语类型)是 scala.AnyVal 的子类型。如果该值等于 x，则使用==(x: Int)方法返回 true，否则返回 false。

> **方法定义:** def ==(x: Int):布尔值
> 
> **返回类型:**如果该值等于 x，则返回真，否则返回假。

**示例#1:**

```
// Scala program of Short ==(x: Int) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short ==(x: Int) function 
        val result = (99.toShort).==(99:Int)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```
true
```

**例 2:**

```
// Scala program of Short ==(x: Int) 
// method 

// Creating object 
object GfG 
{ 

    // Main method 
    def main(args:Array[String]) 
    { 

        // Applying Short ==(x: Int) function 
        val result = (102.toShort).==(101:Int)

        // Displays output 
        println(result) 

    } 
} 
```

**输出:**

```
false
```