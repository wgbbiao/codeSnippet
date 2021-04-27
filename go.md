### golang 前置补0

```golang
func main() {
    a := 1
    fmt.Println(a)
    //前置补0
    fmt.Printf("%03d", a)
    fmt.Println("")
    fmt.Printf("%0*d", 3, a)
}
```
