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
```html
<!DOCTYPE html>
<html>
  <head>
    <title>Quiz</title>
  </head>
  <body>
    <h1>What a great site.</h1>
  </body>
</html>
```

```
The browser is showing a blank page because the title element did not have a closing tag.
```

## Question 2

What's the purpose of the `alt` attribute on image tags?

> Your answer...
```
The purpose of the alt attribute on image tags is to provide a description when the image cannot be seen. Two scenarios in which the alt attribute may come in hand are (1) if the image does not load on the page, or (2) if the visitor to a site is blind.
```

## Question 3

Why does the following code snippet throw an error, and what would fix the error?

```js
var theBody = document.querySelectorAll("body");
theBody.style.backgroundColor = "red";
```

> Your answer...
```
Using "querySelectorAll" requests an array, not a single element. The error is being thrown by the next line - "theBody.style.backgroundColor = "red";" - this line is set up to change the property of an element, not an array. Some ways to approach this are...
var theBody = document.querySelectorAll("body")[0];
var theBody = document.querySelector("body");
var theBody = document.body
```


## Question 4

Why does the following code snippet throw an error, and what would fix the error?

```css
body{
  background-color = "red";
}
```

> Your answer...
```
This is not being read because it does not follow css syntax. In CSS, property-value pairs are declared with a colon (so, they're written like this --- selector{ property: value; }
The "red" value is also throwing an error. In CSS, colors are not in quotations.
```

```css
body{
  background-color: red;
}
```
## Question 5

**The scenario:** You're starting a new app. You create a local repo and a repo on Github, create a readme file, and put it on Github. Then you run into Juan, who's already done a lot of the work you were planning to do. You want to pull his code down and include it in your repo, and put your combined code up on your Github repo.

All the steps for one way of doing the above have been written below, but in the wrong order. Put them in the correct order.

```
$ cd project-repo
$ git init project-repo
$ touch README.md
$ git remote add origin git@github.com/username/project-repo.git
$ git add .
$ git commit -m "initial commit"
$ git push origin master
$ git remote add juan git@github.com/juan/project-repo.git
$ git merge juan/feature
$ git push origin master
```

## Question 6

Your Rails database has two tables. `students` has the columns `id` and `name`, and `sandwiches` has the columns `id`, `type`, and `student_id`.

Use ActiveRecord to create a new `pbj` sandwich and make it belong to the student named Geraldo.

```rb
# Your answer...
geraldo = Student.find_by(name: "Geraldo")
geraldo.sandwiches.create!(type: "pbj")
```

## Question 7

Using Ruby, instantiate an array called `fruits` that contains `apple`, `banana`, and `orange`.

Then, use an enumerator to print to the console the sentence "I'd like to eat a [fruit]" once for each fruit.

```rb
# Your answer...
fruits = ['apple', 'banana', 'orange']
fruits.each do |fruit|
  puts ("I'd like to eat a " + fruit)
end
```

## Question 8

Write one Express route for each of four HTTP methods.

Then, make each route respond with a one-word string containing the RESTful action that would most likely be associated with this route.

```js
var express = require("express");
var app = express();

app.get("/", function(req, res){
  res.send("read");
});
app.post("/", function(req, res){
  res.send("create");
});
app.patch("/:id", function(req, res){
  res.send("update");
});
app.delete("/:id", function(req, res){
  res.send("delete");
});

```

## Question 9

What is the difference between the two following lines of code?

```rb
@artist.save
@artist.save!
```
> Your answer...
```text
Adding a bang (!) to save helps when validation fails to change a database. If an action were implemented without  a bang, the app would fail silently. Adding a bang makes the app throw the error.
```


## Question 10

Using jQuery, write an AJAX request to `http://tunr.com/artists` that would create a new artist with the name of 'Resin Laying Deer Figurine, Gold', and pop up a box saying "All done!" when complete.

```js

$(document).ready(function(){

  var tunrUrl = "http://tunr.com/artists";

  $.ajax({
    url: tunrUrl,
    type: "post",
    data: {artist: "Resin Laying Deer Figurine, Gold"},
    dataType: "json"
  }).done(function(response){
    alert("ALL DONE!");
  }).fail(function(err){
    console.log("Ajax request fails!");
    console.log(err);
  });

});

```

## Question 11

Due to budget cuts, GA can no longer hire new instructors. Instead they can only instantiate new instructors with Javascript.

Define a Javascript constructor called 'Instructor'. Every instance of Instructor should have a `name` property, and a method called `receivePresent`. This method takes one argument called `gift` and, when executed, console-logs "[name] promptly drops the [gift] on the floor."

Instantiate an instructor named 'Andy' and call its `receivePresent` method with "Resin Laying Deer Figurine, Gold" as the argument.

```js

function Instructor(name){
  this.name = name;  
}

Instructor.prototype.receivePresent(gift){
    console.log(this.name+" promptly drops the "+gift+" on the floor.");
}

var andy = new Instructor("Andy");

andy.receivePresent("Resin Laying Deer Figurine, Gold");

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
```text
Some syntax is off. The initial <!DOCTYPE html> tag is missing its' closing parenthesis.
Within the body, yield should be shown as "<%= yield %>"
```

## Question 13

Of the three options below, which is the most "correct" way of organizing the files that make up an Angular app, as used in class? Why is this option considered "better" than the other two?

> Your answer...

```text
B. In Angular, files are sorted by model. (A divides files by controllers/directives/views; C organizes by html and js filetype)
```

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
var andy = new Instructor({
  name: "Andy"
});
andy.save();
andy.wishlist_items.push({description: "Resin Laying Deer Figurine, Gold"});
andy.save();
```
