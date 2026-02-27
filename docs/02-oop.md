# 02 — Object-Oriented Programming (OOP)

## Goal

Ruby on Rails is built entirely around **objects**.

Understanding Object-Oriented Programming (OOP) will help you understand:

- Rails models
- Controllers
- ActiveRecord
- Application structure

This lesson explains only the parts of OOP that Rails actually uses.

---

## What is Object-Oriented Programming?

OOP organizes code using **objects** created from **classes**.

Think of:

- Class → blueprint
- Object → real thing created from blueprint

Example:
```bash
Class: Car
Object: MyCar
```


---

## Classes

A class defines structure and behavior.

```ruby
class User
end
```
This creates a new type called ```User```.

## Creating Objects
Create an object using ```.new```.
```bash
user = User.new
```
Now ```user``` is an instance of the ```User``` class.

## Methods Inside Classes

Classes contain methods (functions).
```bash
class User
  def greet
    "Hello!"
  end
end
```

### Call method:
```bash
user = User.new
user.greet
```

### Output:
```bash
Hello!
```

## Instance Variables

Instance variables store data inside objects.
They start with @.
```ruby
class User
  def set_name(name)
    @name = name
  end

  def get_name
    @name
  end
end
```
### Usage:
```ruby
user = User.new
user.set_name("Alex")
user.get_name
```

## Initialize Method (Constructor)

```initialize``` runs automatically when object is created.
```ruby
class User
  def initialize(name)
    @name = name
  end

  def greet
    "Hello #{@name}"
  end
end
```

### Create object:
```ruby
user = User.new("Alex")
user.greet
```

## Attribute Accessors (Cleaner Way)

Ruby provides shortcuts.

### Instead of writing getters/setters manually:
```ruby
attr_accessor :name
```
### Example:
```ruby
class User
  attr_accessor :name
end

user = User.new
user.name = "Sam"
puts user.name
```
Rails models use this concept internally.

## Instance Methods vs Class Methods
### Instance Method

Works on objects.
```ruby
class User
  def hello
    "Hi"
  end
end
```
### Call:
```ruby
User.new.hello
```

## Class Method

Works on the class itself.
```ruby
class User
  def self.count
    10
  end
end
```

### Call:
```ruby
User.count
```

### Rails example:
```ruby
User.find(1)
```

## Inheritance

A class can inherit behavior from another class.
```ruby
class Animal
  def speak
    "Sound"
  end
end

class Dog < Animal
end
```

### Usage:
```ruby
Dog.new.speak
```

### Output:
```bash
Sound
```

## Why Rails Uses Inheritance

Rails models inherit from:
```ruby
ApplicationRecord
```

### Example:
```ruby
class User < ApplicationRecord
end
```
This gives models database powers automatically.

## Encapsulation (Simple Idea)

Objects manage their own data.

### Instead of changing data everywhere:
```ruby
user.name
```
You interact through methods.
Rails follows this strongly.

## Real Rails Example
### A Rails model:
```ruby
class Post < ApplicationRecord
end
```
is simply a Ruby class with extra abilities added by Rails.
Everything you learned here applies directly.

## Practice Exercise
### Create a file:
```bash
touch oop_practice.rb
```
### Add:
```ruby
class Book
  attr_accessor :title

  def initialize(title)
    @title = title
  end

  def info
    "Book: #{@title}"
  end
end

book = Book.new("Ruby Basics")
puts book.info
```
### Run:
```ruby
ruby oop_practice.rb
```

## Key Concepts to Remember
- Class = blueprint
- Object = instance
- Methods define behavior
- initialize sets starting data
- @variable belongs to object
- Inheritance shares functionality

## Why This Matters for Rails
### Rails components are objects:

| Rails Component | Ruby Concept |
| --------------- | ------------ |
| Model           | Class        |
| Controller      | Class        |
| Record          | Object       |
| ActiveRecord    | Inheritance  |

Understanding OOP makes Rails predictable.

## Summary
### You learned:
- Classes and objects
- Instance variables
- Constructors
- Attribute accessors
- Class vs instance methods
- Inheritance
