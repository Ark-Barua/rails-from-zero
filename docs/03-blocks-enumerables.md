# 03 — Blocks & Enumerables

## Goal

Blocks and Enumerables are core Ruby features heavily used in Rails.

You will see them in:

- database queries
- views
- collections
- iterating records
- background processing

Understanding this lesson makes Rails code much easier to read.

---

## What is a Block?

A block is a piece of code passed to a method.

Example:

```ruby
3.times do
  puts "Hello"
end
```

Output:

```code
Hello
Hello
Hello
```
The code between ```do``` and ```end``` is a block.

## Block Variables

Blocks can receive values.
```ruby
3.times do |i|
  puts i
end
```
Output:
```code
0
1
2
```
```|i|``` is the block variable.

### each — The Most Important Iterator

Rails uses ```each``` everywhere.
```ruby
numbers = [1, 2, 3]

numbers.each do |n|
  puts n
end
```
This loops through each item.

## One-Line Block Syntax

### Ruby allows shorter syntax:
```ruby
numbers.each { |n| puts n }
```
Use ```{}``` for short blocks.
Use ```do...end``` for longer blocks.

## map (Transform Data)

```map``` returns a new array.
```ruby
numbers = [1, 2, 3]

doubled = numbers.map do |n|
  n * 2
end
```

### Result:
```code
[2, 4, 6]
```
Rails uses this for transforming collections.

## select (Filtering)

select filters items.
```ruby
numbers = [1, 2, 3, 4]

evens = numbers.select do |n|
  n.even?
end
```

### Result:
```code
[2, 4]
```

## reject (Opposite of select)
```ruby
numbers.reject { |n| n.even? }
```

### Result:
```code
[1, 3]
```

## find (Locate First Match)
```ruby
numbers.find { |n| n > 2 }
```

### Result:
```code
3
```
Stops after first match.

## Enumerable Module

Arrays include the Enumerable module automatically.

### This gives methods like:
- each
- map
- select
- find
- reduce
Rails collections behave the same way.

### Real Rails Example
#### Controller:
```ruby
@posts.each do |post|
  puts post.title
end
```
#### View (ERB):
```erb
<% @posts.each do |post| %>
  <p><%= post.title %></p>
<% end %>
```
This is used constantly in Rails views.

## Chaining Methods

Enumerable methods can be chained.
```ruby
numbers = [1, 2, 3, 4]

result = numbers
  .select { |n| n.even? }
  .map { |n| n * 10 }
```

### Result:
```code
[20, 40]
```

## reduce (Advanced but Useful)

Combines values into one result.
```ruby
numbers = [1, 2, 3]

sum = numbers.reduce(0) do |total, n|
  total + n
end
```

### Result:
```code
6
```

## Symbol Shortcut

Ruby allows shorthand syntax.

### Instead of:
```ruby
names.map { |name| name.upcase }
```
You can write:
```ruby
names.map(&:upcase)
```
Rails developers use this often.

## Practice Exercise
### Create file:
```bash
touch enumerable_practice.rb
```
### Add:
```ruby
numbers = [5, 10, 15, 20]

result = numbers
  .select { |n| n > 10 }
  .map { |n| n / 5 }

puts result
```
### Run:
```bash
ruby enumerable_practice.rb
```

## Why This Matters for Rails
### Rails query results behave like collections:
```ruby
Post.all.each do |post|
  puts post.title
end
```
ActiveRecord collections use Enumerable internally.

## Summary
### You learned:
- Blocks
- each iterator
- map transformation
- select filtering
- find searching
- method chaining
- enumerable patterns
These patterns appear everywhere in Rails.
