# Go Backend Development

Go is an excellent choice for backend development due to its performance, static binaries, and built-in HTTP support.

### Creating a Basic HTTP Server

You don't need any frameworks to start a web server in Go. The standard library (`net/http`) is enough.

```go
package main

import (
    "fmt"
    "net/http"
)

func helloHandler(w http.ResponseWriter, r *http.Request) {
    fmt.Fprintf(w, "Hello, you've requested: %s\n", r.URL.Path)
}

func main() {
    // 1. Assign a handler function to a route
    http.HandleFunc("/", helloHandler)

    // 2. Start the server on port 8080
    fmt.Println("Server starting on :8080...")
    http.ListenAndServe(":8080", nil)
}
```

### Next Steps in Backend

Once you have the basics down, you can explore:

1.  **JSON APIs**: Use the `encoding/json` package to parse request bodies and return JSON responses.
2.  **Databases**: Use `database/sql` with a driver (like `pq` for Postgres or `go-sql-driver/mysql`) to store data.
3.  **Middleware**: Functions that wrap handlers to provide logging, authentication, or compression.
4.  **Frameworks**: If you need more structure, consider light frameworks like **Gin**, **Echo**, or **Fiber**.