In Go, there are packages and commands to compile and run code.

## Go.MOD

A `Go.mod` file is a file that provides access to operations on Go modules.

To create one for your project, you go to the project root and type `go mod init`

Then add:

```go
module (module_path) // usually "github.com/harsiz/projectName"

go x.xx.x // this is most likely already there
```
## Running / Compilation

`go run` - this runs the go code (You can either specify the file to run OR just run `go run .` in the directory with the main.go file and it will run.)

`go build` - this builds an .exe (or other OS equivalent of a binary).