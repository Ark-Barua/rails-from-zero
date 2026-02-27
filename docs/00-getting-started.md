# 00 — Getting Started

## What is Ruby on Rails?
Ruby on Rails (Rails) is a web framework written in Ruby. It helps you build web apps fast using conventions.

## Recommended setup
- Ruby (latest stable)
- Rails (latest stable)
- Git
- PostgreSQL (recommended for real projects)
- A code editor (VS Code)

## Check versions
```bash
ruby -v
rails -v
git --version
```

## Create a new Rails app
```bash
rails new blog_app
cd blog_app
rails server
```

### Open:
```bash
http://localhost:3000
```

## How to use this repo
- Follow docs in order (00 → 15)
- Try the examples in /examples
- Don’t rush: learn + build small features


---

## 3) `docs/diagrams.md` (Mermaid diagrams render on GitHub)

```md
# Diagrams

## MVC
```mermaid
flowchart LR
A[Browser] --> B[Routes]
B --> C[Controller]
C --> D[Model]
D --> E[Database]
C --> F[View]
F --> A


