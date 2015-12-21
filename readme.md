# WDI7 Cumulative Quiz

## Instructions

1. Fork this repo.
- Clone your fork.
- Fill in your answers by writing the appropriate area, or placing an 'x' in the square brackets for multiple-choice questions.
- Add/Commit/Push your changes to Github.
- Open a pull request.

## Question 1

You've written the following HTML. When you look at it in your browser, it's just blank! Why?

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Quiz
  </head>
  <body>
    <h1>What a great site.</h1>
  </body>
</html>
```

> Your answer...

The title tag has not been closed so the browser is effectively interpreting all of the text as part of the title.

## Question 2

What's the purpose of the `alt` attribute on image tags?

> Your answer...

The 'alt' attribute allows you to enter text that would serve as a descriptive replacement for the image. This is useful if the image fails to load, or if a program for the visually impaired is interpreting your site.

## Question 3

Why does the following code snippet throw an error, and what would fix the error?

```js
var theBody = document.querySelectorAll("body");
theBody.style.backgroundColor = "red";
```

> Your answer...

.querySelectorAll is going to return an array of all elements that match the query. Even though there is only one body, you must select the specific element from the array before you can manipulate it. e.g. theBody[0].style.backgroundColor = "red" or simply use .querySelector instead of .querySelectorAll.

## Question 4

Why does the following code snippet throw an error, and what would fix the error?

```css
body{
  background-color = "red";
}
```

> Your answer...

There should not be any quotes surrounding 'red'.

## Question 5

**The scenario:** You're starting a new app. You create a local repo and a repo on Github, create a readme file, and put it on Github. Then you run into Juan, who's already done a lot of the work you were planning to do. You want to pull his code down and include it in your repo, and put your combined code up on your Github repo.

All the steps for one way of doing the above have been written below, but in the wrong order. Put them in the correct order.

```
$ git init project-repo
$ cd project-repo
$ touch README.md
$ git add .
$ git commit -m "initial commit"
$ git remote add origin git@github.com/username/project-repo.git
$ git push origin master
$ git remote add juan git@github.com/juan/project-repo.git
$ git merge juan/feature
$ git push origin master
```


## Question 6

Your Rails database has two tables. `students` has the columns `id` and `name`, and `sandwiches` has the columns `id`, `type`, and `student_id`.

Use ActiveRecord to create a new `pbj` sandwich and make it belong to the student named Geraldo.

```rb
geraldo = Student.find_by(name: "Geraldo")
geraldo.sandwiches.new(type: "pbj")

```

## Question 7

Using Ruby, instantiate an array called `fruits` that contains `apple`, `banana`, and `orange`.

Then, use an enumerator to print to the console the sentence "I'd like to eat a [fruit]" once for each fruit.

```rb
fruits = ["apple", "banana", "orange"]
fruits.each do |fruit|
  puts "I'd like to eat a #{fruit}"
end

```

## Question 8

Write one Express route for each of four HTTP methods.

Then, make each route respond with a one-word string containing the RESTful action that would most likely be associated with this route.

```js
var express = require("express");
var app = express();

// Your code starts here...
app.get('songs', function(req, res){
  res.send('show')
})

app.post('songs', function(req, res){
  res.send('create')
})

app.put('songs', function(req, res){
  res.send('edit')
})

app.delete('songs', function(req, res){
  res.send('destroy')
})

```

## Question 9

What is the difference between the two following lines of code?

```rb
@artist.save
@artist.save!
```

> Your answer...

.save will return false if any validations fail, while .save! will return an error

## Question 10

Using jQuery, write an AJAX request to `http://tunr.com/artists` that would create a new artist with the name of 'Resin Laying Deer Figurine, Gold', and pop up a box saying "All done!" when complete.

```js
$.ajax({
  url: 'http://tunr.com/artists',
  type: 'post',
  dataType: "json",
  data: {name: "Resin Laying Deer Figurine, Gold"}
}).done(function(){
  alert("All done!")
})

```

## Question 11

Due to budget cuts, GA can no longer hire new instructors. Instead they can only instantiate new instructors with Javascript.

Define a Javascript constructor called 'Instructor'. Every instance of Instructor should have a `name` property, and a method called `receivePresent`. This method takes one argument called `gift` and, when executed, console-logs "[name] promptly drops the [gift] on the floor."

Instantiate an instructor named 'Andy' and call its `receivePresent` method with "Resin Laying Deer Figurine, Gold" as the argument.

```js
function Instructor(name){
  this.name = name;
  this.receivePresent = function(gift){
    console.log(this.name + " promptly drops the " + gift + " to the floor.")
  }
}

var andy = new Instructor("Andy")

andy.receivePresent("Resin Laying Deer Figurine, Gold")

```

## Question 12

Your Rails app has the following `application.html.erb`. Nothing shows up in your browser on any of your app's pages. Why not?

```erb
<!DOCTYPE html
<html>
<head>
  <title>Quiz</title
  <%= stylesheet_link_tag "application", media: "all", "data-turbolinks-track" => true %>
  <%= javascript_include_tag "application", "data-turbolinks-track" => true %>
  <%= csrf_meta_tags %>
</head>
<body>
  <% yield %>
</body>
</html>
```

> Your answer...

There are two tags that have not been closed: <!DOCTYPE html> and </title>

## Question 13

Of the three options below, which is the most "correct" way of organizing the files that make up an Angular app, as used in class? Why is this option considered "better" than the other two?

> Your answer...

Option B represents the way that we have been structuring our Angular apps. This structure makes sense because it is grouping files according to the module that they are associated with. Modules are used to organize and structure our code, and it makes the code more readable to have the file structure mimic the code structure we have created.

### A:
```
/js
  app.js
  controllers/
    artist_index.js
    artist_show.js
  directives/
    artist_form.js
    song_form.js
  views/
    artist_index.html
    artist_show.html
    artist_form.html
    song_form.html
```

### B:
```
/js
  app.js
  artists/
    index.controller.js
    index.html
    show.controller.js
    show.html
    form.directive.js
    form.html
  songs/
    form.html
    form.directive.html
```

### C:
```
/js
  app.js
  controllers/
    artists_controller.js
  directives/
    songs_directive.js
/html
  artists/
    index.html
    show.html
    form.html
  songs/
    form.html
```

## Question 14

Convert the following ActiveRecord sequence to Mongoose:

```rb
@andy = Instructor.find_by(name: "Andy")
@andy.wishlist_items.create(description: "Resin Laying Deer Figurine, Gold")
```

```js
Instructor.find({name: "Andy"}, function(err, docs){
  docs.wishlist_items.push(new WishlistItemModel ({description: "Resin Laying Deer Figurine, Gold"}))
  docs.save()
})

```
