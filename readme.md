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

```
Clark Answer: You forgot the closing title tag "</title>"
```

## Question 2

What's the purpose of the `alt` attribute on image tags?

```
Clark Answer: alt serves two main purposes: 1. specifies the alternative text that is to be rendered when the element which it is applied cannot be rendered. 2. For legal purposes it is used for screen
reading software so a blind person can hear what the image is without see it.
```
## Question 3

Why does the following code snippet throw an error, and what would fix the error?

```js
var theBody = document.querySelectorAll("body");
theBody.style.backgroundColor = "red";
```
```
Clark Answer: When I type this code into chrome's console, the error is "Cannot set property 'backgroundColor' of undefined". There is only one body in a webpage, so I simply deleted
querySelectorAll("body") and changed it to the following:

var body = document.body
body.style.backgroundColor = "red";

Now the chrome console states that the body is "red"!!!
```
## Question 4

Why does the following code snippet throw an error, and what would fix the error?

```css
body{
  background-color = "red";
}
```
```
Clark Answer: The syntax is incorrect for CSS. Is should be written like this:

body {
  background-color: red;
}
```
## Question 5

**The scenario:** You're starting a new app. You create a local repo and a repo on Github, create a readme file, and put it on Github. Then you run into Juan, who's already done a lot of the work you
were planning to do. You want to pull his code down and include it in your repo, and put your combined code up on your Github repo.

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

Your Rails database has two tables. `students` has the columns `id` and `name`, and
`sandwiches` has the columns `id`, `type`, and `student_id`.

Use ActiveRecord to create a new `pbj` sandwich and make it belong to the student named
Geraldo.

```rb
CREATE TABLE students (
id SERIAL PRIMARY KEY,
name TEXT NOT NULL
);

CREATE TABLE sandwiches (
id SERIAL PRIMARY KEY,
type TEXT NOT NULL
student_id INT
);

Geraldo = Student.new(first_name: "Geraldo", sandwhich: "pbj" )

```

## Question 7

Using Ruby, instantiate an array called `fruits` that contains `apples`, `bananas`, and
`oranges`.

Then, use an enumerator to print to the console the sentence "I'd like to eat a [fruit]"
once for each fruit.

```rb
fruits = ['apples', 'bananas', 'oranges']

var fruits = ["apples", "bananas", "oranges"];
for(var i = 0; i < fruits.length; i++) {
  console.log("I like to eat " + fruits[i]);
}

```

## Question 8

Write one Express route for each of four HTTP methods.

Then, make each route respond with a one-word string containing the RESTful action that
would most likely be associated with this route.

```js
var express = require("express");
var app = express();

app.post("/create" function(req,res){
  res.send("create comment here")
});

app.get("/read", function (req, res) {
  res.send("read comments here")
});

app.put("/update", function(req,res){
  res.send("update comment here")
});

app.delete("/delete", function(req,res){
  res.send("Comment delete")
});

```

## Question 9

What is the difference between the two following lines of code?

```rb
@artist.save
@artist.save!
```

Clark Answer: Methods with and ! attached to the end of them usually mean that they will
modify the object they are calling on. Save! will raise an error if not successful. Save
will return true or false

## Question 10

Using jQuery, write an AJAX request to `http://tunr.com/artists` that would create a new
artist with the name of 'Resin Laying Deer Figurine, Gold', and pop up a box saying "All
done!" when complete.

```js
$(document).ready(function(){
  $("h1").on("click", function(){
    var url =
    "http://tunr.com/artists"
    $.ajax({
      url: url,
      type: "get",
      dataType: "json"
    }).done(function(){
    alert("All done!")

```

## Question 11

Due to budget cuts, GA can no longer hire new instructors. Instead they can only instantiate
new instructors with Javascript.

Define a Javascript constructor called 'Instructor'. Every instance of Instructor should
have a `name` property, and a method called `receivePresent`. This method takes one argument
called `gift` and, when executed, console-logs "[name] promptly drops the [gift] on the
floor."

Instantiate an instructor named 'Andy' and call its `receivePresent` method with "Resin
Laying Deer Figurine, Gold" as the argument.

```js
function Person(initialName) {
  this.name = initialName;
  this.species = "Homo Sapiens";
  this.speak = function() {return "Hello! I'm " + this.name};
}

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

## Question 13

Of the three options below, which is the most "correct" way of organizing the files that make up an Angular app, as used in class? Why is this option considered "better" than the other two?

> Your answer...

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
// Your answer...
```
