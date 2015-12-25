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

There does not appear to be a closing tag for the title, which might be a problem (although I always assumed the browser is smart enough to make assumptions and close off missing tags). All the other tags open and close correctly so that's the only thing that looks off to me.

## Question 2

What's the purpose of the `alt` attribute on image tags?

To allow those with screen readers who may not be able to view the image an alternative way to understand what the image represents. You fill the alt attribute with text and that's what the screen reader will read. It provides better accessibility.
## Question 3

Why does the following code snippet throw an error, and what would fix the error?

```js
var theBody = document.querySelectorAll("body");
theBody.style.backgroundColor = "red";
```

It looks like using querySelectorAll is the culprit. There should only be one body tag per page and querySelectorAll returns us a node list (array) which we cannot style. We can overcome this bug by using querySelector since we know there will only be one body tag, or use querySelectorAll('body')[0] to select the first body tag and style it that way.

## Question 4

Why does the following code snippet throw an error, and what would fix the error?

```css
body{
  background-color = "red";
}
```

The value of a css property should never be enclosed in quotes. It's a syntactic rule of the language.

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
geraldo = Student.find_by(name: 'Geraldo')
pbj = geraldo.sandwiches.create(type: 'pbj')
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

```js
var express = require("express");
var app = express();

app.get('/song', function(req, res){
  res.send('All song')
})

app.post('/song', function(req, res){
  res.send('Made new song')
})

app.put('/song/:id', function(req, res){
  res.send('Updated song')
})

app.delete('/song/:id', function(req, res){
  res.send('Deleted song')
})

```

## Question 9

What is the difference between the two following lines of code?

```rb
@artist.save
@artist.save!
```

The latter uses a bang to modify the actual value and to provide extra (verbose) errors if something goes wrong.

## Question 10

Using jQuery, write an AJAX request to `http://tunr.com/artists` that would create a new artist with the name of 'Resin Laying Deer Figurine, Gold', and pop up a box saying "All done!" when complete.

```js

$.ajax({
  method: "POST",
  url: "http://tunr.com/artists",
  data: { name: "Resin Laying Deer Figurine, Gold"}
}).done(function(data) {
    alert("All done!");
  })

```

## Question 11

Due to budget cuts, GA can no longer hire new instructors. Instead they can only instantiate new instructors with Javascript.

Define a Javascript constructor called 'Instructor'. Every instance of Instructor should have a `name` property, and a method called `receivePresent`. This method takes one argument called `gift` and, when executed, console-logs "[name] promptly drops the [gift] on the floor."

Instantiate an instructor named 'Andy' and call its `receivePresent` method with "Resin Laying Deer Figurine, Gold" as the argument.

```js
function Instructor (name) {
  this.name = name;

  this.receivePresent = function (gift) {
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

There is nothing defined above the yield tag (no text or tags, such as headers), that would be shared across all the views. It is completely empty, so as far as the app is considered all it sees is the empty space between the empty opening and closing body tags.
## Question 13

Of the three options below, which is the most "correct" way of organizing the files that make up an Angular app, as used in class? Why is this option considered "better" than the other two?

Not too sure about this one without doing extra researching, but my gut tells me B looks like the correct answer. I recall everything tied to a particular resource (directives, views, controllers) being put under a single folder instead of separated out under more folders. I believe the reason for that (as shown in B) is because conventionally we would have something like an index.controller.js and an index.html and they show up next to each other, which is easier to keep track off. In terms of index.controller.js (and other file names) I believe it has to be written like that instead of spine case like in the other two options. Spine case should only ever be in the HTML for the most part.
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
var andy = Instructor.findOne({name: 'Andy'}, function(err, person){
  if (err) {
    console.log('No person found by that name')
  } else {
    console.log('The name is ' + person.name)
  }
})

andy.wishlistItems.create({description: 'Resin Laying Deer Figurine, Gold'}, function(err, data){
  if (err) {
    console.log('error creating new wishlist item')
  } else {
    console.log('Successfully created ' + data + 'wishlist item')
  }
}) //camelcase for JS?

// not sure how right this is - I also feel like there's a way to save the wishlist items at the
// same time in the callback to findOne?

```
