Go has a `net/url` package in the standard library. It lets you convert a _URL_ into a struct and extract certain stuff from it.

E.g - You can __Extract the Hostname__ by using `url.Parse()` :

```go
parsedURL := url.Parse("https://example.com")

hostName := parsedURL.Hostname()
```