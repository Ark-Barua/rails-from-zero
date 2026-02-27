# Contributing Guide

Thank you for helping improve this learning resource.

This repository is designed to remain a **clear, beginner-friendly Ruby on Rails learning path**. Contributions should prioritize clarity, simplicity, and practical understanding.

---

## Goals of This Repository

- Help beginners learn Ruby on Rails step-by-step
- Provide clean explanations and examples
- Avoid unnecessary complexity
- Stay framework-focused and practical

---

## Ways You Can Contribute

You can help by:

- Fixing typos or grammar issues
- Improving explanations
- Adding clearer examples
- Updating outdated Rails commands
- Adding diagrams or visual explanations
- Improving formatting or readability

---

## Contribution Rules

Please follow these guidelines:

### 1. Keep It Beginner Friendly
Assume readers have little or no prior Rails experience.

Avoid:
- Advanced jargon without explanation
- Overly complex solutions
- Large theoretical discussions

Prefer:
- Simple explanations
- Step-by-step instructions
- Practical examples

---

### 2. Keep Content Neutral
- Do not add personal branding
- Do not promote products or services
- Avoid self-promotion links

This repo is community learning material.

---

### 3. Formatting Standards

Use consistent Markdown formatting:

#### Headings

# Main Title
## Section
### Subsection



#### Code Blocks
Use language labels:

```ruby
class User < ApplicationRecord
end
```
```ruby
rails generate model Post title:string
```

### 4. File Organization
- Lessons belong inside ```bash /docs```
- Examples go inside ```bash /examples```
- Diagrams go inside ```bash /diagrams```
- Keep filenames descriptive

Example:
```bash
docs/08-full-crud.md
```

### How to Contribute (Step-by-Step)
1. Fork the repository
2. Create a new branch:
   ```bash
   git checkout -b improve-auth-lesson
   ```
3. Make your changes
4. Commit clearly:
   ```bash
   git commit -m "Improve authentication explanation"
   ```
5. Push your branch:
   ```bash
   git push origin improve-auth-lesson
   ```
6. Open a Pull Request

#### Pull Request Guidelines

A good PR should:
- Explain what changed
- Explain why it helps learners
- Stay focused on one improvement
- Avoid unrelated edits

#### Code of Respect

Be respectful and constructive.

We welcome:
- Beginners
- First-time contributors
- Documentation contributors
Learning-focused collaboration is encouraged.

#### Questions?

Open an Issue describing:
- what is unclear
- what you want to improve
- suggested changes

Thank you for helping make learning accessible for everyone.
