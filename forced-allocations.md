# Don't force allocations on the callers of your API

This is a principle of API design inspired by [this blog post](https://dave.cheney.net/2019/09/05/dont-force-allocations-on-the-callers-of-your-api) by Dave Cheney. For performance reasons, you should allow users to control memory allocations in their program.

## Examples in Go

The `io.Reader.Read` method has the signature:
```go
func (r *Reader) Read(buf []byte) (int, error)
```

> `io.Reader` is the only Go interface in widespread use that returns *both* a result *and* an error.

Why? For performance reasons! It forces a user to specify the buffer to read into because then the control is in the user's hands.

### `CopyBuffer` and `sync.Pool`

There are examples in Go where this principle hasn't been followed.

The `io.Copy` function automatically allocated a buffer. This led to the Go team having to implement another function, `io.CopyBuffer` which allowed users to pass in a buffer. See <https://go-review.googlesource.com/c/go/+/8730>.

In other cases, like the `fmt` and `net/http` packages, it wasn't possible to just add new functions. Furthermore, the Go 1 guarantee prevents the APIs of these packages from changing. This led to the adoption of `sync.Pool`, a data structure that lets you save and reuse temporary objects across goroutines. 