## Notes

* 这个库我觉得核心的点就是演示了如何用 golang 中的 http.Client 去发送请求, 还有就是命令行程序的写法了。
    核心的实现就是在 request 中加入了 httptrace 模块, 用 httptrace 去获得请求的各个阶段的数据, 还有
    定义 http.Transport 用 tls 发送 https 的请求调用。
* golang 这种方式的调用老子总以为是高阶函数的调用
    ```
    grayscale(14)("/")

    func grayscale(code color.Attribute) func(string, ...interface{}) string {
        return color.New(code + 232).SprintfFunc()
    }

    ```





# httpstat

[![Build Status](https://travis-ci.org/davecheney/httpstat.svg?branch=master)](https://travis-ci.org/davecheney/httpstat)

![Shameless](./screenshot.png)

Imitation is the sincerest form of flattery.

But seriously, https://github.com/reorx/httpstat is the new hotness, and this is a shameless rip off.

## Installation
`httpstat` requires Go 1.7.1 or later.
```
$ go get -u github.com/davecheney/httpstat
```	
## Usage
```
$ httpstat https://example.com/
```
## Features

- Windows/BSD/Linux supported.
- HTTP and HTTPS are supported, for self signed certificates use `-k`.
- Skip timing the body of a response with `-I`.
- Follow 30x redirects with `-L`.
- Change HTTP method with `-X METHOD`.
- Provide a `PUT` or `POST` request body with `-d string`. To supply the `PUT` or `POST` body as a file, use `-d @filename`.
- Add extra request headers with `-H 'Name: value'`.
- The response body is usually discarded, you can use `-o filename` to save it to a file, or `-O` to save it to the file name suggested by the server.
- HTTP/HTTPS proxies supported via the usual `HTTP_PROXY`/`HTTPS_PROXY` env vars (as well as lower case variants).
- Supply your own client side certificate with `-E cert.pem`.

## Contributing

Bug reports are most welcome, but with the exception of #5, this project is closed.

Pull requests must include a `fixes #NNN` or `updates #NNN` comment. 

Please discuss your design on the accompanying issue before submitting a pull request. If there is no suitable issue, please open one to discuss the feature before slinging code. Thank you.
