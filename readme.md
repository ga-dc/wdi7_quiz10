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
```There is no closing tag for the title tag.

## Question 2

What's the purpose of the `alt` attribute on image tags?

> It's purpose is so screen readers who may not be able to view the image can understand what the image is
in a short description. Which is shown as text for the screen reader to read.

## Question 3

Why does the following code snippet throw an error, and what would fix the error?

```js
var theBody = document.querySelectorAll("body");
theBody.style.backgroundColor = "red";
```
The querySelectorAll is what is causing the error. There should only be one body tag
per page and querySelectorAll returns an node list which cannot be styled. To fix this
use querySelector since there is only one body tag. Could also use querySelectorAll('body')[0],
this you could use to select the first body tag.

## Question 4

Why does the following code snippet throw an error, and what would fix the error?

```css
body{
  background-color = "red";
}
```

The css property value should not be in quotes.

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
#
geraldo = Student.find_by(name: 'Geraldo')
pbj = geraldo.sandwiches.create(type: 'pbj')
```

## Question 7

Using Ruby, instantiate an array called `fruits` that contains `apple`, `banana`, and `orange`.

Then, use an enumerator to print to the console the sentence "I'd like to eat a [fruit]" once for each fruit.

```rb
# Your answer...
fruits = ['apple', 'banana', 'orange']
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
app.get('/song', function(req,res){
  res.send('All song')
})

app.post('/song', function(req,res){
  res.send('Made new song')
})

app.put('/song/:id', function(req,res){
  res.send('Updated song')
})

app.delete('/song/:id', function(req,res){
  res.send('Deleted song')
})
```

## Question 9

What is the difference between the two following lines of code?

```rb
@artist.save
@artist.save!
```

> Your answer...

@artist.save! is being banged which modifies the actual value and provides extra errors if
something goes wrong
## Question 10

Using jQuery, write an AJAX request to `http://tunr.com/artists` that would create a new artist with the name of 'Resin Laying Deer Figurine, Gold', and pop up a box saying "All done!" when complete.

```js
// Your code starts here...
$.ajax({
  method: "POST"
  url: "http://tunr.com/artists",
  data: {name: "Resin Laying Deer Figurine, Gold"}
}).done(function(data){
  alert("All done!")
})
```

## Question 11

Due to budget cuts, GA can no longer hire new instructors. Instead they can only instantiate new instructors with Javascript.

Define a Javascript constructor called 'Instructor'. Every instance of Instructor should have a `name` property, and a method called `receivePresent`. This method takes one argument called `gift` and, when executed, console-logs "[name] promptly drops the [gift] on the floor."

Instantiate an instructor named 'Andy' and call its `receivePresent` method with "Resin Laying Deer Figurine, Gold" as the argument.

```js
// Your code starts here...
function Instructor (name) {
  this.name = name;

  this.receivePresent = function (gift){
    console.log(this.name + 'promptly drops the ' + this.gift + 'on the floor.')
  }
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

Nothing is defined above the yield tag that would be shared across all the views. It is completely empty so all
the app is see is empty space between the empty opening and closing tags.  Also the yield tag is missing =


## Question 13

Of the three options below, which is the most "correct" way of organizing the files that make up an Angular app, as used in class? Why is this option considered "better" than the other two?

> Your answer...

The answer would be B. I believe the reason for that (as shown in B) is because conventionally we would have something like an index.controller.js and an index.html and they show up next to each other, which is easier to keep track off. In terms of index.controller.js (and other file names) I believe it has to be written like that instead of spine case like in the other two options. Spine case should only ever be in the HTML for the most part.
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
var andy = Instructor.findOne({name: 'Andy'} function(err, person){
  if (err) {
    console.log('No person found by that name')
  }else{
    console.log('The name is ' + person.name)
  }
})

andy.wishlistItems.create({description: 'Resin Laying Deer Figurine, Gold'}, function(err,data){
  if(err){
    console.log('error creating new wishlist item')
  }else{
    console.log('Successfully created ' + data + 'wishlist item.')
  }
})
```
