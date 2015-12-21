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

I've forgotten to close my title tag.
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


## Question 2

What's the purpose of the `alt` attribute on image tags?

The 'alt' tag is key for accessibility. If the image is unable to render as an image or is disabled on the client side, then your end user can still understand the purpose of that image.

## Question 3

Why does the following code snippet throw an error, and what would fix the error?

```js
var theBody = document.querySelectorAll("body");
theBody.style.backgroundColor = "red";
```

> Your answer...

## Question 4

Why does the following code snippet throw an error, and what would fix the error?

```css
body{
  background-color = "red";
}
```

Incorrect syntax. To fix the error, change the equal sign to a colon and remove the parenthesis from around "red".

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

Jen's Answer
First, let's find Geraldo (an already existing student).
```rb
geraldo = Student.where(name: "Geraldo")
```

Now I can use this variable to assign our new sandwich to Geraldo.

```rb
pbj = Sandwich.create(type: 'pbj', student: geraldo)

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

//CREATE
app.post("/cats", function(req, res){
  console.log("create")
});

//READ
app.get("/cats", function(req, res){
  console.log("index")
});

//UPDATE
app.put("/cats/:cat_id", function(req, res){
  console.log("update")
});

// Destroy
app.delete("/cats/:cat_id", function(req, res){
  console.log("delete")
})

```

## Question 9

What is the difference between the two following lines of code?

```rb
@artist.save
@artist.save!
```

Both instances will save a record. The second version with the added bang ensures that the app will throw an error if a validation fails. Without the bang, it fails silently meaning I wouldn't know if the validation failed without checking.

## Question 10

Using jQuery, write an AJAX request to `http://tunr.com/artists` that would create a new artist with the name of 'Resin Laying Deer Figurine, Gold', and pop up a box saying "All done!" when complete.

```js
$(".create_new_artist").on("click", function(){
  $.ajax({
    type: 'POST',
    data: {artist: {name: "Resin Laying Deer Figurine, Gold", nationality: "Target", photo_url: "http://scene7.targetimg1.com/is/image/Target/26390613?wid=480&hei=480",}},
    dataType: 'json',
    url: "http://tunr.com/artists"
  }).done(function(response) {
    console.log("All done!");
  }).fail(function(response){
    console.log("Create failed");
  })
})
```

## Question 11

Due to budget cuts, GA can no longer hire new instructors. Instead they can only instantiate new instructors with Javascript.

Define a Javascript constructor called 'Instructor'. Every instance of Instructor should have a `name` property, and a method called `receivePresent`. This method takes one argument called `gift` and, when executed, console-logs "[name] promptly drops the [gift] on the floor."

Instantiate an instructor named 'Andy' and call its `receivePresent` method with "Resin Laying Deer Figurine, Gold" as the argument.

```js

function Instructor(name) {
  this.name = name;
  this.receivePresent = function(gift) {
    console.log(this.name + " promptly drops the " + gift + " on the floor.");
  }
};

var andy = new Instructor("Andy");
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

I need to include a equal sign within the party had to render the yield.

<%= yield %>

## Question 13

Of the three options below, which is the most "correct" way of organizing the files that make up an Angular app, as used in class? Why is this option considered "better" than the other two?

Jen's Answer:

Option B is the most "correct" way demonstrated of the three options. This approach keeps views and controllers for a particular feature grouped together. With Angular, best practices in organization revolve around making sure the code is modular and grouping features into little mini applications. Cited benefits include scalability, maintainability, debugging, and testing.

*  [Resource](https://scotch.io/tutorials/angularjs-best-practices-directory-structure)

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
var andy = Instructor.find(function, (err, instructors){
  if (err) return console.log(err);
})

andy.wishlist_items.save({description: "Resin Laying Deer Figurine, Gold"});
```
