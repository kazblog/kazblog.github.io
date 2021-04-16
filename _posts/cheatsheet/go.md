### moduleが無いよ系のエラー
main.go:7:3: no required module provides package github.com/gin-gonic/gin: go.mod file not found in current directory or any parent directory; see 'go help modules'go: no module declaration in go.mod. To specify the module path:

go mod edit -module=example.com/mod



```bash
go mod init example.com/hoge/hello
```

go.mod内に、こう記述される。
↓
```go
module example.com/hoge/hello
```


<br><br>
```bash
go get github.com/gin-gonic/gin   
```


go.mod内に、こう記述される。
↓
```go
require github.com/gin-gonic/gin v1.7.1 // indirect
```
