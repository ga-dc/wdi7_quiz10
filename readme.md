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

> Your answer...The title tag is not closed, which means that the rest of the HTML is being read as part of the title tag, which does not render in the browser. Adding </title> on line 19 would solve this problem.

## Question 2

What's the purpose of the `alt` attribute on image tags?

> Your answer...The 'alt' attribute makes descriptive information about an image available in the browser window if the image file fails to load, and it also makes the descriptive text available to those with a visual impairment who are using a screen reader.

## Question 3

Why does the following code snippet throw an error, and what would fix the error?

```js
var theBody = document.querySelectorAll("body");
theBody.style.backgroundColor = "red";
```

> Your answer...querySelectorAll() returns an array, even if it only contains one element, so to successfully select the body, you would need to type 'theBody[0].style.backgroundColor = 'red''
The task of setting the background color to red could be accomplished in a single line of code using jQuery as follows: $("body").css("background-color", "red");

## Question 4

Why does the following code snippet throw an error, and what would fix the error?

```css
body{
  background-color = "red";
}
```

> Your answer...red in this context is a value, not a string, so it should not be inside quotation marks. Also, css using : not an = between key value pairs, so it should be written as background-color: red;

## Question 5

**The scenario:** You're starting a new app. You create a local repo and a repo on Github, create a readme file, and put it on Github. Then you run into Juan, who's already done a lot of the work you were planning to do. You want to pull his code down and include it in your repo, and put your combined code up on your Github repo.

All the steps for one way of doing the above have been written below, but in the wrong order. Put them in the correct order.
<!-- I think a step is missing below - wouldn't you need to do a git fetch from juan's remote branch to be able to pull down his feature branch before you could merge it into your own repo? -->

```
$ git init project-repo
$ cd project-repo
$ git remote add origin git@github.com/username/project-repo.git
$ touch README.md
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
geraldo = Student.create(name: "Geraldo")
newSandwich = Sandwich.create(type: "pbj", student_id: 1)
```

## Question 7

Using Ruby, instantiate an array called `fruits` that contains `apple`, `banana`, and `orange`.

Then, use an enumerator to print to the console the sentence "I'd like to eat a [fruit]" once for each fruit.

```rb
# Your answer...
fruits = ["apple", "banana", "orange"]
fruits.each { |fruit| print "I'd like to eat a {fruit}!" }
```

## Question 8

Write one Express route for each of four HTTP methods.

Then, make each route respond with a one-word string containing the RESTful action that would most likely be associated with this route.

```js
var express = require("express");
var app = express();

// Your code starts here...If this was a blog app, the following routes could be used to create, show/read, update, and delete posts:
var postsController = {
  show: function(req, res){
    return "show"
  },
  create: function(req, res){
    return "create"
  },
  update: function(req, res){
    return "update"
  },
  delete: function(req, res){
    return "delete"
  }
};

app.get("/posts/:user_id", postsController.show);
app.post("/posts", postsController.create);
app.put("/posts/:user_id", postsController.update)
app.delete("/posts/:user_id", postsController.delete);
```

## Question 9

What is the difference between the two following lines of code?

```rb
@artist.save
@artist.save!
```

> Your answer...@artist.save! will return an error if the save action is unsuccessful...@artist.save will return a boolean value so you can write an if/else statement that will respond to either a true or false statement resulting from the save action.

## Question 10

Using jQuery, write an AJAX request to `http://tunr.com/artists` that would create a new artist with the name of 'Resin Laying Deer Figurine, Gold', and pop up a box saying "All done!" when complete.

```js
// Your code starts here..
$.ajax({
  type: 'POST',
  url: 'http://tunr.com/artists',
  data: { name: "Resin Laying Deer Figurine, Gold"},
  success: function(){
    alert('All done!')
  }
});

```

## Question 11

Due to budget cuts, GA can no longer hire new instructors. Instead they can only instantiate new instructors with Javascript.

Define a Javascript constructor called 'Instructor'. Every instance of Instructor should have a `name` property, and a method called `receivePresent`. This method takes one argument called `gift` and, when executed, console-logs "[name] promptly drops the [gift] on the floor."

Instantiate an instructor named 'Andy' and call its `receivePresent` method with "Resin Laying Deer Figurine, Gold" as the argument.

```js
// Your code starts here...
function Instructor(name){
  this.name = name;
  this.receivePresent = function receivePresent(gift) {
    console.log(name + ' promptly drops the ' + gift + ' on the floor.')
  };
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

> Your answer...Both the DOCTYPE tag and the title tag are missing their closing bracket, therefore everything in the body is being read as data from the head.

## Question 13

Of the three options below, which is the most "correct" way of organizing the files that make up an Angular app, as used in class? Why is this option considered "better" than the other two?

> Your answer...In class we have organized our files similar to example B. I think this is because the html is so tied to the controllers and directives that it makes the most sense to keep all files associated with one model in the same folder.

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
Model.findOne({ name: "Andy"}, function (err, doc){
  doc.wishlist_items.push(description: "Resin Laying Deer Figurine, Gold");
  doc.save();
});
```
