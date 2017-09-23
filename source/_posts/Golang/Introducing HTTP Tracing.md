title: Golang HTTP 跟踪
date: 2016-11-7
tags: golang
---

Go 官方博客之 [Introducing HTTP Tracing](https://blog.golang.org/http-tracing)

## 简介
在 Go 1.7 版本我们介绍了 HTTP 跟踪功能，用于收集 HTTP 客户端整改生命周期下的请求信息。通过包 **net/http/httptrace** 实现 HTTP 跟踪功能。收集的信息可用于寻找隐藏的 bug，监控服务等方面。

## HTTP 事件
*httptrace* 包对 HTTP 运行过程中的事件提供了钩子处理，这些事件包括:
* 连接创建
* 连接被使用
* DNS 查询
* 写请求
* 读响应

## 事件跟踪
通过创建一个 [*httptrace.ClientTrace](https://golang.org/pkg/net/http/httptrace/#ClientTrace)钩子函数并设置在[context.Context](https://golang.org/pkg/context/#Context)上开启 HTTP 跟踪。
通过[http.RoundTripper](https://golang.org/pkg/net/http/#RoundTripper)激活相关的事件和钩子函数。

```
   req, _ := http.NewRequest("GET", "http://example.com", nil)
    trace := &httptrace.ClientTrace{
        DNSDone: func(dnsInfo httptrace.DNSDoneInfo) {
            fmt.Printf("DNS Info: %+v\n", dnsInfo)
        },
        GotConn: func(connInfo httptrace.GotConnInfo) {
            fmt.Printf("Got Conn: %+v\n", connInfo)
        },
    }
    req = req.WithContext(httptrace.WithClientTrace(req.Context(), trace))
    if _, err := http.DefaultTransport.RoundTrip(req); err != nil {
        log.Fatal(err)
    }
```

在请求中，http.DefaultTransport 会在每个事件发生时调用一次, 上面请求会在查询 DNS 结束时打印出相关信息,同样也会在连接建立时打印连接信息。

## 跟踪 http.Client
这个跟踪功能是为跟踪单个 http.Transport.RoundTrip 的生命周期内事件设计。尽管如此, 客户端可能会为了完成一个 HTTP 请求而创建多个 round trips。例如, 当一个 URL 重定向时，相关的钩子函数会被调用多次并创建多个请求。
用户会在 http.Client 层识别响应时间，下面程序的请求即通过  http.RoundTripper 封装。

```
package main

import (
    "fmt"
    "log"
    "net/http"
    "net/http/httptrace"
)

// transport is an http.RoundTripper that keeps track of the in-flight
// request and implements hooks to report HTTP tracing events.
type transport struct {
    current *http.Request
}

// RoundTrip wraps http.DefaultTransport.RoundTrip to keep track
// of the current request.
func (t *transport) RoundTrip(req *http.Request) (*http.Response, error) {
    t.current = req
    return http.DefaultTransport.RoundTrip(req)
}

// GotConn prints whether the connection has been used previously
// for the current request.
func (t *transport) GotConn(info httptrace.GotConnInfo) {
    fmt.Printf("Connection reused for %v? %v\n", t.current.URL, info.Reused)
}

func main() {
    t := &transport{}

    req, _ := http.NewRequest("GET", "https://google.com", nil)
    trace := &httptrace.ClientTrace{
        GotConn: t.GotConn,
    }
    req = req.WithContext(httptrace.WithClientTrace(req.Context(), trace))

    client := &http.Client{Transport: t}
    if _, err := client.Do(req); err != nil {
        log.Fatal(err)
    }
}
```
这个程序会从 google.com 重定向到 www.google.com 并输出如下结果

```
Connection reused for https://google.com? false
Connection reused for https://www.google.com/? false
```

Transport 位于 net/http 包，并支持 HTTP1 和 HTTP2 请求。

如果你需要定制  http.RoundTripper 的实现, 你可以支持对 *httptest.ClientTrace 的跟踪。

## 总结

HTTP 跟踪是一个对那些调试 HTTP 隐藏请求和网络流量很有价值的工具，开启这个功能让我们希望社区有更多相关的调试和可视化工具---例如[httpstat](https://github.com/davecheney/httpstat)