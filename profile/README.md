<h1 align="center">coregx</h1>

<p align="center">
  <strong>High-Performance Go Libraries</strong><br>
  Production-grade. Zero CGO. Minimal dependencies.
</p>

<p align="center">
  <a href="https://github.com/coregx"><img src="https://img.shields.io/badge/Go-1.25+-00ADD8?style=flat&logo=go" alt="Go Version"></a>
  <a href="https://github.com/coregx"><img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="License"></a>
  <a href="https://github.com/coregx"><img src="https://img.shields.io/badge/CGO-Zero-brightgreen?style=flat" alt="Zero CGO"></a>
</p>

---

## Ecosystem

### Text Processing

| Library | Description | Stars | Status |
|:--------|:------------|:-----:|:------:|
| **[coregex](https://github.com/coregx/coregex)** | Regex engine, 3-3000x faster than stdlib, SIMD | [![](https://img.shields.io/github/stars/coregx/coregex?style=flat-square&label=)](https://github.com/coregx/coregex) | v0.9.1 |
| **[ahocorasick](https://github.com/coregx/ahocorasick)** | Aho-Corasick multi-pattern matching | [![](https://img.shields.io/github/stars/coregx/ahocorasick?style=flat-square&label=)](https://github.com/coregx/ahocorasick) | v0.2.x |

### Web & HTTP

| Library | Description | Stars | Status |
|:--------|:------------|:-----:|:------:|
| **[fursy](https://github.com/coregx/fursy)** | HTTP router, type-safe handlers, OpenAPI gen | [![](https://img.shields.io/github/stars/coregx/fursy?style=flat-square&label=)](https://github.com/coregx/fursy) | Active |
| **[stream](https://github.com/coregx/stream)** | SSE & WebSocket, RFC-compliant, zero deps | [![](https://img.shields.io/github/stars/coregx/stream?style=flat-square&label=)](https://github.com/coregx/stream) | v1.x |

### Data & Messaging

| Library | Description | Stars | Status |
|:--------|:------------|:-----:|:------:|
| **[relica](https://github.com/coregx/relica)** | Type-safe SQL query builder, zero prod deps | [![](https://img.shields.io/github/stars/coregx/relica?style=flat-square&label=)](https://github.com/coregx/relica) | Active |
| **[pubsub](https://github.com/coregx/pubsub)** | Pub/Sub with DLQ, backoff, clean architecture | [![](https://img.shields.io/github/stars/coregx/pubsub?style=flat-square&label=)](https://github.com/coregx/pubsub) | Active |

### Reactive

| Library | Description | Stars | Status |
|:--------|:------------|:-----:|:------:|
| **[signals](https://github.com/coregx/signals)** | Reactive state, Angular-inspired, zero allocs | [![](https://img.shields.io/github/stars/coregx/signals?style=flat-square&label=)](https://github.com/coregx/signals) | Active |

### Documents

| Library | Description | Stars | Status |
|:--------|:------------|:-----:|:------:|
| **gxpdf** | Pure Go PDF generation & manipulation | — | Coming Soon |

---

## Highlights

### coregex — 3-3000x Faster Regex

Cross-language benchmarks on 6MB input ([source](https://github.com/kolkov/regex-bench)):

| Pattern | Go stdlib | coregex | Rust regex | vs stdlib |
|---------|-----------|---------|------------|-----------|
| IP validation | 493 ms | 3.2 ms | 12 ms | **154x** |
| Inner `.*keyword.*` | 231 ms | 1.9 ms | 0.6 ms | **122x** |
| Suffix `.*\.txt` | 233 ms | 1.8 ms | 1.4 ms | **127x** |
| Literal alternation | 473 ms | 4.2 ms | 0.7 ms | **113x** |

**Beats Rust regex on IP patterns by 2.7x!** 13 specialized engines, SIMD acceleration, O(n) guaranteed.

### relica — Type-Safe SQL

```go
users := relica.Select("id", "name").
    From("users").
    Where(relica.Eq("active", true)).
    OrderBy("created_at DESC").
    Limit(10)
```

Advanced features: JOINs, subqueries, CTEs, window functions. 3x faster batch operations.

### fursy — Modern HTTP Router

```go
r := fursy.New()
r.Get("/users/{id}", handlers.GetUser)  // Type-safe params
// Auto-generates OpenAPI 3.1 spec
```

RFC 9457 errors, built-in validation, minimal dependencies.

---

## Philosophy

- **Zero CGO** — Simple `go build`, no C compiler needed
- **Minimal Dependencies** — Only what's absolutely necessary
- **Production-Grade** — Battle-tested, well-documented, maintained
- **Go 1.25+** — Modern Go features, generics where useful

---

## Powered by coregx

| Project | Description | Using |
|:--------|:------------|:------|
| **[uawk](https://github.com/kolkov/uawk)** | Ultra AWK interpreter, 19x faster than GoAWK | coregex |

---

## Contributing

We welcome contributions! See individual repository CONTRIBUTING.md files.

**Areas where we need help:**
- Real-world testing and bug reports
- Documentation and examples
- Performance optimization ideas

---

## License

All projects are licensed under the **MIT License**.

---

<p align="center">
  <sub>Production-grade Go libraries for demanding applications</sub><br>
  <a href="https://github.com/coregx">github.com/coregx</a>
</p>
