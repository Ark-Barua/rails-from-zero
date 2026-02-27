# 04 — Files, Modules & Gems

## Goal

In this lesson you will learn how Ruby projects are organized.

These concepts explain how Rails works internally:

- How Ruby loads files
- How code is organized using modules
- How external libraries (gems) work
- How Bundler manages dependencies

Rails applications are simply structured Ruby projects using these ideas.

---

## Working With Files

Ruby code is usually split across multiple files.

Example structure:
```bash
project/
main.rb
helper.rb
```

---

## Loading Files with `require`

Ruby loads another file using `require`.

### helper.rb

```ruby
def greet(name)
  "Hello #{name}"
end
```

### main.rb

```ruby
require "./helper"
puts greet("Alex")
```

### Run:
ruby main.rb

---

```require``` vs ```require_relative```
### require

Used for installed libraries (gems).
```ruby
require "json"
```

### require_relative

Used for files inside your project.
```ruby
require_relative "helper"
```
Rails automatically manages file loading for you.

---

## Modules

Modules group related code together.
They prevent naming conflicts and organize functionality.

---

## Creating a Module
```ruby
module Greetings
  def self.hello
    "Hello!"
  end
end
```

### Use it:
```ruby
Greetings.hello
```
---

## Why Modules Matter

Imagine two classes both having a method called format.
Modules help separate logic safely.
Rails uses modules everywhere.

---

## Including Modules

Modules can add behavior to classes.
```ruby
module Speak
  def talk
    "Talking"
  end
end

class User
  include Speak
end

User.new.talk
```
This is called mixins.
Rails uses this pattern heavily.

---

## Namespacing with Modules

Modules can wrap classes.
```ruby
module Admin
  class User
  end
end
```
### Access:
```ruby
Admin::User.new
```
### Rails example:
```ruby
Api::PostsController
```
This keeps large apps organized.

---

## What is a Gem?

A gem is a reusable Ruby library.

### Examples:

- database connectors
- authentication systems
- payment integrations
- background job tools
Rails itself is a gem.

---

## Installing a Gem
```ruby
gem install colorize
```

### Use it:
```ruby
require "colorize"
puts "Hello".colorize(:red)
```

---

## Bundler (Dependency Manager)

Real projects use Bundler to manage gems.
Bundler ensures everyone uses the same versions.

---

## Gemfile

Every Rails app has a ```Gemfile```.

### Example:
```ruby
source "https://rubygems.org"

gem "rails"
gem "pg"
```
---

## Install Dependencies
```ruby
bundle install
```
Bundler downloads all gems.

---

## Gemfile.lock
This file locks exact versions.
Never edit manually.
Always commit it to Git.

---

## How Rails Uses Gems

Rails apps rely on many gems:
- Devise → authentication
- Sidekiq → background jobs
- Pundit → authorization
- RSpec → testing
Rails loads them automatically.

---

## Load Paths (Conceptual)

Ruby searches for files in load paths.
Rails configures this automatically so you rarely worry about it.
That is why Rails can find models and controllers without manual require.

---

## Practice Exercise

### Create project:
```bash
mkdir ruby_modules
cd ruby_modules
```
### Create file:
```bash
touch math_tools.rb
```
### Add:
```ruby
module MathTools
  def self.square(n)
    n * n
  end
end
```
### Create another file:
```bash
touch app.rb
```
### Add:
```ruby
require_relative "math_tools"

puts MathTools.square(5)
```
### Run:
```bash
ruby app.rb
```
---

## Why This Matters for Rails

### Rails automatically:

- loads files
- organizes modules
- manages dependencies
- connects gems
Understanding this explains Rails project structure.

---

## Summary
### You learned:
- Loading files
- require vs require_relative
- Modules
- Mixins
- Namespacing
- Gems
- Bundler
- Gemfile workflow
These concepts power every Rails application.

---
