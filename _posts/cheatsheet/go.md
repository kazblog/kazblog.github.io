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
