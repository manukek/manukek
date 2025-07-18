
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
    github    githubStats
}

type githubStats struct {
    totalStars  int
    totalRepos  int
    totalForks  int
    followers   int
    following   int
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

func (m *manukq) githubStats() {
    fmt.Println("\n=> github.stats()")
    fmt.Printf("   %-10s: %d\n", "stars", m.github.totalStars)
    fmt.Printf("   %-10s: %d\n", "repos", m.github.totalRepos)
    fmt.Printf("   %-10s: %d\n", "forks", m.github.totalForks)
    fmt.Printf("   %-10s: %d\n", "followers", m.github.followers)
    fmt.Printf("   %-10s: %d\n", "following", m.github.following)
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
        tools:     []string{"Git", "NGINX", "Figma", "json/json5"},
        contacts: map[string]string{
            "discord":  "manukq_",
            "telegram": "@manukqq",
            "github":   "github.com/manukek",
        },
        github: githubStats{
            totalStars:  18,
            totalRepos:  17,
            totalForks:  3,
            followers:   8,
            following:   20,
        },
    }
    
    dev.whoami()
    dev.stack()
    dev.githubStats()
    dev.connect()
    
    fmt.Println("\n// server started on port :8080")
    fmt.Println("\n// localhost:8080\n 127.0.0.1:8080")
}

```
```go
// bash
go run main.go
```
