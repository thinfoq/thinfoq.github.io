# Gin 框架简介


Gin 框架简介
<!--more-->

## Gin 简介

Gin 是一个用 Go (Golang) 编写的 HTTP Web 框架。 它具有类似 Martini 的 API，但性能比 Martini 快 40 倍。如果你需要极好的性能，使用 Gin 吧。

## 快速入门

要求：Go 1.13 及以上版本

要安装 Gin 软件包，需要先安装 Go 并设置 Go 工作区。

1.下载并安装 gin：
```shell
$ go get -u github.com/gin-gonic/gin
```
2.将 gin 引入到代码中：
```Go
import "github.com/gin-gonic/gin"
```
3.（可选）如果使用诸如 http.StatusOK 之类的常量，则需要引入 net/http 包：
```Go
import "net/http"
```
4.示例代码：
```Go
package main

import (
	"net/http"

	"github.com/gin-gonic/gin"
)

func main() {
	r := gin.Default()
	r.GET("/ping", func(ctx *gin.Context) {
		ctx.JSON(http.StatusOK, gin.H{
			"message": "pong",
		})
	})
	r.Run()
}
```
浏览器访问：
```url
http://localhost:8080/ping
```
返回:
```JSON
{
  "message": "pong"
}
```

