To call a get request in Golang, you first add the `net/http` library and then you:

### GET REQUEST (Client)
```go
package main

import "net/http"

res, err := http.Get("https://api.whatever.com")
```