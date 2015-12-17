# WDI7 Cumulative Quiz

## Instructions

1. Fork this repo.
- Clone your fork.
- Fill in your answers by writing the appropriate area, or placing an 'x' in the square brackets for multiple-choice questions.
- Add/Commit/Push your changes to Github.
- Open a pull request.

## Question 1

Why does the following code snippet throw an error, and what would fix the error?

```js
var theBody = document.querySelectorAll("body");
theBody.style.backgroundColor = "red";
```

> `querySelectorAll` always returns an array of elements, even when that array includes just one element. This can be fixed with `document.body`, `document.querySelectorall("body")[0]`, or `document.querySelector("body")`.

## Question 2

Why does the following code snippet throw an error, and what would fix the error?

```css
body{
  background-color = "red";
}
```

> CSS properties are followed by a colon, not an equals sign.

## Question 3

**The scenario:** You're starting a new app. You create a local repo and a repo on Github, create a readme file, and put it on Github. Then you run into Juan, who's already done a lot of the work you were planning to do. You want to pull his code down and include it in your repo, and put your combined code up on your Github repo.

All the steps for one way of doing the above have been written below, but in the wrong order. Put them in the correct order.

```
$ git init 
$ touch README.md
$ git add .
$ git commit -m "initial commit"
$ git remote add origin git@github.com/username/project-repo.git
$ git push origin master
$ git remote add juan git@github.com/juan/project-repo.git
$ git merge juan/feature
$ git push origin master
```

## Question 4


One of the lines of code in the following snippet will throw an error. Which one is it, and why?

```js
/*1*/ "use strict";
/*2*/ var max = 100;
/*3*/ for(i = 1; i < max; i++){
/*4*/   if(i % 15 == 0) console.log("FizzBuzz");
/*5*/   else if(i % 3 == 0) console.log("Fizz");
/*6*/   else if(i % 5 == 0) console.log("Buzz");
/*7*/   else console.log(i);
/*8*/ }
```

> Line 3 will throw an error. `use strict` prevents you from using any variables without declaring them first with `var`. `i` hasn't been declared.

## Question 5

Using Ruby, instantiate an array called `fruits` that contains `apple`, `banana`, and `orange`.

Then, use an enumerator to print to the console the sentence "I'd like to eat a [fruit]" once for each fruit.

```rb
# Your answer...

fruits = ["apple", "banana", "orange"]
fruits.each do |fruit|
  puts "I'd like to eat a #{fruit}"
end
```

## Question 6

Write one Express route for each of four HTTP methods.

Then, make each route respond with a one-word string containing the RESTful action that would most likely be associated with this route.

```js
var express = require("express");
var app = express();

// Your code starts here...

app.get("/", function(request, response){
  response.send("SHOW");
});
app.post("/", function(request, response){
  response.send("CREATE");
});
app.put("/:id", function(request, response){
  response.send("UPDATE");
});
app.delete("/:id", function(request, response){
  response.send("DELETE");
});
// `app.patch` is also acceptable
// Not including `:id` is acceptable.
```

## Question 7

What is the difference between the two following lines of code?

```rb
@artist.save
@artist.save!
```

> If validations fail, the first line will fail silently, while the second line will throw a fatal error.

## Question 8

Using jQuery, write an AJAX request to `http://tunr.com/artists` that would create a new artist with the name of 'Resin Laying Deer Figurine, Gold', and pop up a box saying "All done!" when complete.

```js
// Your code starts here...

$.ajax({
  method: "POST",
  url: "http://tunr.com/artists",
  dataType: "json",
  data: {
    name: "Resin Laying Deer Figurine, Gold"
  }
}).done(function(){
  alert("All done!");
});
```

## Question 9

Due to budget cuts, GA can no longer hire new instructors. Instead they can only instantiate new instructors with Javascript.

Define a Javascript constructor called 'Instructor'. Every instance of Instructor should have a `name` property, and a method called `receivePresent`. This method takes one argument called `gift` and, when executed, console-logs "[name] promptly drops the [gift] on the floor."

Instantiate an instructor named 'Andy' and call its `receivePresent` method with "Resin Laying Deer Figurine, Gold" as the argument.

```js
// Your code starts here...

function Instructor(name){
  this.name = name;
}
Instructor.prototype.receivePresent = function(gift){
  console.log(this.name + " promptly drops the " + gift + " on the floor.");
}

var andy = new Instructor("Andy");
andy.receivePresent("Resin Laying Deer Figurine, Gold");
```

## Question 10

Of the three options below, which is the most "correct" way of organizing the files that make up an Angular app? Why is this option considered "better" than the other two?

> **B** is correct. Angular is made up of templates and components that are very closely-linked. In this layout, related components are listed right next to each other in alphabetical order.

> `A` and `C` would require a lot of jumping from folder to folder because they don't reflect the intertwinedness of HTML and JS in Angular. `C` does not reflect the "one view, one controller" paradigm.

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

