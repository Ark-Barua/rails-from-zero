# 06 — Models, Migrations & ActiveRecord

## Goal

In this lesson you will learn how Rails works with databases.

You will understand:

- What models are
- What migrations do
- How Rails stores data
- ActiveRecord basics
- Creating and querying records

This is where Rails becomes a real application framework.

---

## What is a Model?

A **Model** represents data in your application.

Example:
- User
- Post
- Comment

Each model usually corresponds to a **database table**.

Example:

| Model | Database Table |
|-------|----------------|
|  User |     users      |
|  Post |     posts      |

---

## Generate a Model

### Create a Post model:
```bash
rails generate model Post title:string content:text
```

### Rails creates:
```code
app/models/post.rb
db/migrate/TIMESTAMP_create_posts.rb
```

---

## Migration Files

A migration describes changes to the database.

### Example migration:
```ruby
class CreatePosts < ActiveRecord::Migration[7.0]
  def change
    create_table :posts do |t|
      t.string :title
      t.text :content

      t.timestamps
    end
  end
end
```
Migrations are version control for your database.

---

## Run the Migration
### Apply database changes:
```bash
rails db:migrate
```
Rails now creates the ```posts``` table.

---

## Database Schema
### After migration, check:
```code
db/schema.rb
```
### You will see:
```ruby
create_table "posts"
```
This file represents the current database structure.

---

## ActiveRecord

ActiveRecord is Rails’ ORM (Object Relational Mapper).

## It connects:
```code
Ruby Objects ⇄ Database Tables
```
You work with Ruby objects instead of SQL.

---

## Creating Records
### Open Rails console:
```bash
rails console
```
### Create a post:
```ruby
Post.create(title: "Hello", content: "My first post")
```
Record saved to database.

---

## Reading Records
### Get all posts:
```ruby
Post.all
```
### Find one:
```ruby
Post.find(1)
```
### Find first:
```ruby
Post.first
```

---

## Updating Records
```ruby
post = Post.find(1)
post.update(title: "Updated Title")
```
---

## Deleting Records
```ruby
post.destroy
```
Record removed from database.

---

## Validations

Models can enforce rules.

### Open:
```code
app/models/post.rb
```
### Add:
```ruby
class Post < ApplicationRecord
  validates :title, presence: true
end
```
Now Rails prevents empty titles.

---

## Test Validation
### In console:
```ruby
Post.create(content: "Missing title")
```
This will fail validation.

---

## Timestamps
### Rails automatically adds:
```ruby
created_at
updated_at
```
Useful for tracking data changes.

## Rails Console (Important Tool)

Console lets you test models quickly.

### Start:
```bash
rails console
```
### Exit:
```ruby
exit
```
You will use console constantly during development.

---

## Model Naming Rules

### Rails conventions:

| Model | Table |
| ----- | ----- |
| Post  | posts |
| User  | users |
Singular model → plural table.

---

## Practice Exercise

1. Generate a model:
```bash
rails generate model Article title:string body:text
```
2. Run migration:
```bash
rails db:migrate
```
3. Open console.
4. Create 3 articles.
5. Fetch all articles.

---

## Why ActiveRecord Matters

### Without ActiveRecord:
```SQL
INSERT INTO posts ...
SELECT * FROM posts;
```
### With Rails:
```ruby
Post.create(...)
Post.all
```
Cleaner and safer.

---

## Summary
### You learned:
- Models represent data
- Migrations change database structure
- ActiveRecord handles queries
- CRUD operations
- Validations
- Rails console usage
You can now store and manage real data.

---
