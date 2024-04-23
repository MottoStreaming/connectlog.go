# Connect log package
[![PkgDoDev][godev:image]][godev:url]

This package contains Connect interceptor that uses `slog.Logger` to log 
results of handler calls.

Note: we have `gcpconnect.go` package that wraps this package and some other standard interceptors.

By default, it doesn't log when handler returns `nil` error. 
This can be changed by using `connectlog.WithSuccess()`.

Example:
```go
	path, handler := xxxconnect.NewXXXServiceHandler(
		service,
		connect.WithInterceptors(connectlog.NewLoggingInterceptor(logger)),
		connect.WithRecover(connectlog.NewLoggingRecoverHandler(logger)),
	)
```

[godev:image]:  https://pkg.go.dev/badge/github.com/MottoStreaming/connectlog.go
[godev:url]:    https://pkg.go.dev/github.com/MottoStreaming/connectlog.go
