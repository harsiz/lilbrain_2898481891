Part of [[Golang Backend]], Works well with [[Go HTTP]]

Mutexes in Go let you lock access to data.
This is so you can control what goroutines can access certain data and at specific times.

```md
Mutex is short for mutual exclusion, and the conventional name for the data structure that provides it is "mutex", often abbreviated to "mu".

It's called "mutual exclusion" because a mutex _excludes_ different threads (or goroutines) from accessing the same data at the same time.
```

Information: `Maps are NOT thread safe!` For concurrent use, if they are being written to, there needs to be a mutex lock on the maps so no problems regarding goroutines mixing together with it.

It's also good to use `defer mutex.Unlock()` right at the start so you don't forget to unlock your mutex.

```go

import "sync"
mu := sync.Mutex

// ... (pseudo code)
var count int
go func() {
	mu.Lock()
	defer mu.Unlock()
	count++ // must be locked so race conditions dont happen
}()
```