### golang 前置补0

```go
func main() {
    a := 1
    fmt.Println(a)
    //前置补0
    fmt.Printf("%03d", a)
    fmt.Println("")
    fmt.Printf("%0*d", 3, a)
}
```

### 取调用函数的名称 

Caller报告当前go程调用栈所执行的函数的文件和行号信息。实参skip为上溯的栈帧数，0表示Caller的调用者（Caller所在的调用栈）。（由于历史原因，skip的意思在Caller和Callers中并不相同。）函数的返回值为调用栈标识符、文件名、该调用在文件中的行号。如果无法获得信息，ok会被设为false。

```go
package main
import (
	"fmt"
	"runtime"
)
func main() {
	Foo()
}
func Foo() {
	fmt.Printf("我是 %s, %s 在调用我!\n", printMyName(), printCallerName())
	Bar()
}
func Bar() {
	fmt.Printf("我是 %s, %s 又在调用我!\n", printMyName(), printCallerName())
}
func printMyName() string {
	pc, _, _, _ := runtime.Caller(1)
	return runtime.FuncForPC(pc).Name()
}
func printCallerName() string {
	pc, _, _, _ := runtime.Caller(2)
	return runtime.FuncForPC(pc).Name()
}
```

