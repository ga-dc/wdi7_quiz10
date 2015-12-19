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

The <title> tag is not closed.  Insert </title> at the end of line 17.

## Question 2

What's the purpose of the `alt` attribute on image tags?

The alt attribute gives a description for the image if for some reason the person trying to access the page cannot see it.

## Question 3

Why does the following code snippet throw an error, and what would fix the error?

```js
var theBody = document.querySelectorAll("body");
theBody.style.backgroundColor = "red";
```

There is only one body element in traditional html so I would use querySelector.  

var theBody= document.querySelector("body");
theBody.style.backgroundColor = "red";

## Question 4

Why does the following code snippet throw an error, and what would fix the error?

```css
body{
  background-color = "red";
}
```

red does not need to be in quotations if we are defining it within our css.

body{
  background-color = red;
}

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

```rb
Student.create(id: 1, name: "Geraldo")
Sandwich.create(type: "pbj", student_id: 1)

```

## Question 7

Using Ruby, instantiate an array called `fruits` that contains `apple`, `banana`, and `orange`.

Then, use an enumerator to print to the console the sentence "I'd like to eat a [fruit]" once for each fruit.

```rb
fruits = ['apple', 'banana', 'orange']

fruits.each do |fruit|
  puts "I'd like to eat a #{fruit}"
end

```

## Question 8

Write one Express route for each of four HTTP methods.

Then, make each route respond with a one-word string containing the RESTful action that would most likely be associated with this route.

create read update delete

```js
var express = require("express");
var app = express();

app.get('/', function(req, res){
  res.send('Read')
})

app.post('/', function(req, res){
  res.send('Create')
})

app.put('/', function(req, res){
  res.send('Update')
})

app.delete('/', function(req, res){
  res.send('Delete')
})

```

## Question 9

What is the difference between the two following lines of code?

```rb
@artist.save
@artist.save!
```

save! will raise an error if it is not successful and save will return true or false.

## Question 10

Using jQuery, write an AJAX request to `http://tunr.com/artists` that would create a new artist with the name of 'Resin Laying Deer Figurine, Gold', and pop up a box saying "All done!" when complete.

```js
var url = "http://tunr.com/artists"
$.ajax({
  url: url,
  type: "post",
  data: {artist: {name: "Resin Laying Deer Figurine, Gold"}},
  dataType: "json"
}).done(function(response){
      alert("All done!");
    }).fail(function(response){
      console.log("Ajax request fails!");
    }).always(function(response){
      console.log("This always happens regardless of successful ajax request or not.");
    })
  })
})

```

## Question 11

Due to budget cuts, GA can no longer hire new instructors. Instead they can only instantiate new instructors with Javascript.

Define a Javascript constructor called 'Instructor'. Every instance of Instructor should have a `name` property, and a method called `receivePresent`. This method takes one argument called `gift` and, when executed, console-logs "[name] promptly drops the [gift] on the floor."

Instantiate an instructor named 'Andy' and call its `receivePresent` method with "Resin Laying Deer Figurine, Gold" as the argument.

```js
var Instructor = function(name){
  this.name = name;
  this.receivePresent = function(gift){
    console.log(name+"promptly drops the "+gift+" on the floor.");
  }
}
Andy = new Instructor("Andy");
Andy.receivePresent("Resin Laying Deer Figurine, Gold")
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

There is no "=" in the yield on line 208.

## Question 13

Of the three options below, which is the most "correct" way of organizing the files that make up an Angular app, as used in class? Why is this option considered "better" than the other two?
```
> B
This option is considered most correct because of what is being separated.  Separating by concerns for angular means putting like directives, controllers, and views in the same folder for the model that they are dealing with.
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
var andy = Instructor.find({'name': 'Andy'}, function(err, users){
  if (err) throw err;
});

var andrew = andy.Wishlist_Item.create({description: 'Resin Laying Deer Figurine, Gold'});
andy.save(function(err){
  if (err) return handleError(err);
})

```
