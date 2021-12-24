# 反映。Golang 中的 IsNil()函数示例

> 原文:[https://www . geesforgeks . org/reflect-is nil-function-in-golang-with-examples/](https://www.geeksforgeeks.org/reflect-isnil-function-in-golang-with-examples/)

Go 语言提供了运行时反射的内置支持实现，并允许程序在反射包的帮助下操作任意类型的对象。**反映。Golang 中的 IsNil()** 函数用于检查其自变量 v 是否为零。参数必须是 chan、func、接口、映射、指针或切片值；如果不是，IsNil 就会恐慌。

**注意:** IsNil 并不总是等同于围棋中与零的常规比较。例如，如果通过使用未初始化的接口变量 I 调用 ValueOf 来创建 v，i==nil 将为真，但是 *v.IsNil* 将会死机，因为 v 将是零值。

> **语法:**
> 
> ```
> func (v Value) IsNil() bool
> 
> ```
> 
> **参数:**此功能不接受任何参数。
> 
> **返回值:**该函数返回其参数 v 是否为零。

以下示例说明了上述方法在 Golang 中的使用:

**例 1:**

```
// Golang program to illustrate
// reflect.IsNil() Function

package main

import (
    "bytes"
    "fmt"
)

// Main function
func main() {
    var body *bytes.Buffer
    fmt.Printf("main(): body == nil ? %t\n", body == nil)
}
```

**输出:**

```
main(): body == nil ? true

```

**例 2:**

```
// Golang program to illustrate
// reflect.IsNil() Function 

package main

import (
    "fmt"
    "reflect"
)

func isNilFixed(i interface{}) bool {
   if i == nil {
      return true
   }
   switch reflect.TypeOf(i).Kind() {
   case reflect.Ptr, reflect.Map, reflect.Array, reflect.Chan, reflect.Slice:
    //use of IsNil method
    return reflect.ValueOf(i).IsNil()
   }
   return false
}

// Main function 
func main() {
    t := reflect.TypeOf(5)

    arr := reflect.ArrayOf(4, t)
    inst := reflect.New(arr).Interface().(*[4]int)

    for i := 1; i <= 4; i++ {
        inst[i-1] = i*i
    }

    fmt.Println(isNilFixed(inst))
}
```

**输出:**

```
false

```