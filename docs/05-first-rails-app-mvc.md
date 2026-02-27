# 05 — First Rails App & MVC

## Goal

In this lesson you will:

- Create your first Rails application
- Understand the MVC architecture
- Learn how a request moves through Rails
- See how routes, controllers, and views work together

This is where Rails officially begins.

---

## What is MVC?

Rails follows the **MVC pattern**.

MVC stands for:

- **Model** → Data & business logic
- **View** → What users see
- **Controller** → Connects Model and View

```bash
User → Controller → Model → Database
↓
View → Browser
```
MVC keeps applications organized and scalable.

---

## Create Your First Rails App

Run:

```bash
rails new blog_app
cd blog_app
```
---

## Start the server:
```ruby
rails server
```
---

## Open in browser:
```ruby
http://localhost:3000
```
You should see the Rails welcome page.

---

## Rails Folder Structure (Important)

### Inside your project:
```bash
blog_app/
├── app/
│   ├── controllers/
│   ├── models/
│   ├── views/
├── config/
├── db/
├── Gemfile
```
### Key folders:

| Folder      | Purpose          |
| ----------- | ---------------- |
| controllers | request handling |
| models      | database logic   |
| views       | UI templates     |
| db          | database schema  |

---

## Step 1 — Generate a Controller
### Create a controller:
```bash
rails generate controller Pages home
```
### Rails creates:
```bash
app/controllers/pages_controller.rb
app/views/pages/home.html.erb
```

---

## Step 2 — Controller
### Open:
```ruby
app/controllers/pages_controller.rb
class PagesController < ApplicationController
  def home
  end
end
```
The method home is called an action.

---

## Step 3 — Route
### Open:
```bash
config/routes.rb
```
### Add:
```ruby
root "pages#home"
```
### Meaning:
```code
controller#action
```
### So Rails connects:
```code
PagesController → home action
```

---

## Step 4 — View
### Open:
```code
app/views/pages/home.html.erb
```
### Add:
```erb
<h1>Hello Rails</h1>
<p>Your first Rails page works.</p>
```
Refresh browser.
You now have a working Rails page.

---

## Request Flow (Very Important)
### When user visits a page:
1. Browser sends request
2. Routes file checks URL
3. Controller action runs
4. Controller loads data
5. View renders HTML
6. Response sent back
### Flow:
```code
Browser
   ↓
Routes
   ↓
Controller
   ↓
View
   ↓
Browser
```

---

## Controller Responsibility
### Controllers should:
- receive requests
- prepare data
- render views

### Example:
```ruby
def home
  @message = "Welcome!"
end
```

---

## Passing Data to Views
### Controller:
```ruby
def home
  @message = "Hello from controller"
end
```
### View:
```erb
<p><%= @message %></p>
```
```@``` variables are accessible in views.

---

## ERB Basics
### Rails views use ERB.

#### Output value
```erb
<%= "Hello" %>
```
#### Run Ruby code (no output)
```erb
<% if true %>
  <p>Visible</p>
<% end %>
```

---

## Layouts

Rails wraps views inside a layout.

### File:
```code
app/views/layouts/application.html.erb
```
### Your page content appears inside:
```erb
<%= yield %>
```
This is the page placeholder.

---

## Generate Another Page
### Add action:
```ruby
def about
end
```
### Add route:
```ruby
get "about", to: "pages#about"
```
### Create view:
```code
app/views/pages/about.html.erb
```
### Now visit:
```code
/about
```

---

## Rails Naming Convention
### Rails depends on naming rules:

| Component    | Naming          |
| ------------ | --------------- |
| Controller   | plural          |
| Model        | singular        |
| Views folder | controller name |

### Example:
```code
PostsController
views/posts/
Post model
```
Follow conventions to avoid errors.

---

## Practice Exercise

1. Create a new controller:
```bash
rails generate controller Welcome index
```
2. Set as root route.
3. Display a welcome message.
4. Add another page called ```/contact```.

---

## Why MVC Matters
### Without MVC:
- code becomes messy
- logic mixes with UI
- hard to scale

### With MVC:
- clean separation
- easier debugging
- team-friendly structure
Rails enforces MVC automatically.

---

## Summary
### You learned:
- What MVC is
- Rails project structure
- Controllers
- Routes
- Views
- ERB basics
- Request lifecycle
You have now built your first Rails flow.
