# 01 — Ruby Basics

## Goal

Before learning Rails, you need to understand the parts of Ruby that Rails uses every day.

This lesson focuses only on **practical Ruby**, not academic theory.

---

## Running Ruby Code

You can run Ruby in two ways:

### Interactive mode (REPL)

```bash
irb
```

Now you can type Ruby code directly:
```bash
2 + 2
```
Exit with:
```bash
exit
```

## Running a Ruby file
### Create a file:
```bash
touch hello.rb
```
## Add:
```bash
puts "Hello Ruby"
```

## Run:
```bash
ruby hello.rb
```

## Variables
Ruby variables store values.
```bash
name = "Alex"
age = 25
is_active = true
```
Ruby automatically detects types.
No ```int```, ```string```, or ```boolean``` keywords needed.

#### Naming Rules

## Good:
```bash
user_name
total_price
```

## Avoid:
```bash
UserName
total-price
```
Ruby uses snake_case.

## Data Types
### Strings
```bash
title = "Rails Guide"
Numbers
count = 10
price = 19.99
```
### Booleans
```bash
true
false
```
### Nil (empty value)
```bash
value = nil
```
## String Interpolation
### Insert variables inside strings:
```bash
name = "Sam"
puts "Hello #{name}"
```
### Output:
```bash
Hello Sam
```

## Arrays

Arrays store lists.
```bash
fruits = ["apple", "banana", "mango"]
```

### Access items:
```bash
fruits[0]
```

### Add items:
```bash
fruits << "orange"
```

## Hashes (Very Important for Rails)

Hashes store key-value pairs.
```bash
user = {
  name: "Alex",
  age: 25
}
```

### Access values:
```bash
user[:name]
```
Rails heavily uses hashes for params and configs.

## Conditionals
### if statement
```bash
age = 18

if age >= 18
  puts "Adult"
end
```

### if / else
```bash
if age >= 18
  puts "Adult"
else
  puts "Minor"
end
```

## Methods

Methods define reusable logic.
```bash
def greet(name)
  "Hello #{name}"
end
```

### Call method:
```bash
greet("Alex")
```

## Return Values

Ruby returns the last line automatically.
```bash
def add(a, b)
  a + b
end
```
No ```return``` needed.

## Loops
### each loop (most common in Rails)
```bash
numbers = [1, 2, 3]

numbers.each do |n|
  puts n
end
```
You will see this everywhere in Rails views.

## Symbols (Rails Favorite)

### Symbols look like this:
```bash
:name
:email
:user_id
```

### Used for:
- hashes
- params
- Rails configuration

Example:
```bash
{ name: "Alex" }
Comparison Operators
==   # equal
!=   # not equal
>    # greater than
<    # less than
>=   # greater or equal
<=   # less or equal
```

## Truthy vs Falsy
### In Ruby:
#### Falsy values:
- ```false```
- ```nil```
Everything else is truthy.
```bash
if 0
  puts "Runs!"
end
```
This still runs.

## Simple Practice
### Try in IRB:
```bash 
user = { name: "Sam", age: 20 }

if user[:age] > 18
  puts "Access granted"
end
```

## Why This Matters for Rails
### Rails code constantly uses:
- hashes → params
- arrays → collections
- methods → controllers
- loops → views
- symbols → configuration
Learning these basics makes Rails much easier.

## Summary
### You learned:
- Running Ruby
- Variables
- Data types
- Arrays & hashes
- Conditionals
- Methods
- Loops
- Symbols
