Part of [[Golang Backend]]

To call a get request in Golang, you first add the `net/http` library and then you:

### GET REQUEST (Client)
```go
package main

import "net/http"

res, err := http.Get("https://api.whatever.com")
```

## JSON

### JSON decode

We can decode JSON bytes (or strings) into a Go struct using [`json.Unmarshal`](https://pkg.go.dev/encoding/json#Unmarshal) or a [`json.Decoder`](https://pkg.go.dev/encoding/json#Decoder).

The `Decode` method of `json.Decoder` streams data from an [`io.Reader`](https://pkg.go.dev/io#Reader) into a Go struct, while `json.Unmarshal` works with data that's already in `[]byte` format. 

Using a `json.Decoder` can be more memory-efficient because it doesn't load all the data into memory at once. `json.Unmarshal` is ideal for small JSON data you already have in memory. When dealing with HTTP requests and responses, you will likely use `json.Decoder` since it works directly with an `io.Reader`.

### JSON Decoding (Decoder )
This is for http requests. This is an example:

```go
package main

import (
	"fmt"
	"net/http"
	"encoding/json"
)

type BitcoinReq struct {
	Usd float64 `json:"usd"`
}

type SolanaReq struct {
	Usd float64 `json:"usd"`
}

type APIResponse struct {
	Bitcoin BitcoinReq `json:"bitcoin"`
	Solana SolanaReq `json:"solana"`
}

func main() {
	var a APIResponse
	res, err := http.Get("https://api.coingecko.com/api/v3/simple/price?ids=bitcoin,solana&vs_currencies=usd")
	
	if err != nil {
		fmt.Println(err)
		return
	}
	decoder := json.NewDecoder(res.Body)
	err = decoder.Decode(&a)
	
	fmt.Printf("Bitcoin Price: %.2f\nSolana Price: %.2f\n", a.Bitcoin.Usd, a.Solana.Usd)
}
```


## HTTP Options / Settings

### HTTP headers

HTTP headers allow clients & servers to pass additional info with each request / response. They are __case-insensitive__ key-value pairs that pass additional metadata about the req/resp.

Most HTTP requests by default carry many headers such as:
- Type of client (like Google Chrome / Firefox)
- The OS (like windows or mac)
- The preferred language (like English or Italian)