
```go
// main.go
package main

import (
    "fmt"
    "strings"
)

type manukq struct {
    name      string
    role      string
    languages []string
    frontend  []string
    backend   []string
    databases []string
    tools     []string
    contacts  map[string]string
}

func (m *manukq) whoami() {
    fmt.Printf("=> %s.whoami()\n", strings.ToLower(m.name))
    fmt.Printf("   %s - %s\n", m.name, m.role)
}

func (m *manukq) stack() {
    stacks := map[string][]string{
        "languages": m.languages,
        "frontend":  m.frontend,
        "backend":   m.backend,
        "databases": m.databases,
        "tools":     m.tools,
    }
    
    fmt.Println("\n=> stack()")
    for key, items := range stacks {
        fmt.Printf("   %-10s: %s\n", key, strings.Join(items, ", "))
    }
}

func (m *manukq) connect() {
    fmt.Println("\n=> connect()")
    for platform, contact := range m.contacts {
        fmt.Printf("   %-10s: %s\n", platform, contact)
    }
}

func main() {
    dev := &manukq{
        name: "Manukq",
        role: "Программист-самоучка",
        languages: []string{"JavaScript", "TypeScript", "C#", "Go"},
        frontend:  []string{"HTML5", "CSS3", "Next.js", "Tailwind CSS"},
        backend:   []string{"Node.js", ".NET"},
        databases: []string{"MongoDB", "MySQL"},
        tools:     []string{"Git", "NGINX", "Figma","json/json5"},
        contacts: map[string]string{
            "discord":  "manukq_",
            "telegram": "@manukqq",
            "github":   "github.com/manukek",
        },
    }
    
    dev.whoami()
    dev.stack()
    dev.connect()
    
    fmt.Println("\n// server started on port :8080")
    fmt.Println("\n// localhost:8080\n 127.0.0.1:8080")
}

```
```go
// bash
go run main.go
```
