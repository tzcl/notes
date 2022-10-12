# `errors.Wrap` was originally written by Dave Cheney

Go 1.13 introduced new features to the `errors` and `fmt` packages to simplify working with errors that contain other errors. This included unwrapping errors, `errors.Is`, `errors.As` and `fmt.Errorf` and `%w`.

These were inspired by Dave Cheney's https://github.com/pkg/errors. Yes, the same Dave Cheney that has that Go blog.