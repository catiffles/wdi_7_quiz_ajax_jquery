# JQuery/Ajax Quiz

Write your answer below each question.

### Question 1
(a) What is a click handler?

-A click handler triggers an event when the specified object is clicked

(b) Where in your JS file should you put it, and WHY?

-It should be within the document ready section of the JS file to watch for clicks after the HTML is loaded.

### Question 2
If you get the error `$ is undefined`, what does that mean and what could you do to fix it?

-Load jQuery before JS files

### Question 3
What should go in the `$(document).ready()` part of your JS file?

-Functions that watch for certain behaviors (click, mouseover, etc) and link to other functions that tell the browser what to do.

### Question 4
In an AJAX GET request, what does the argument of the `.done()` callback - in the example below, that would be `data` - represent?

```
$.ajax({
    url: 'http://ig-hacker-news.herokuapp.com/users',
    type: 'GET',
  })
  .done(function(data) {
    console.log("success!")
  });
```

-the argument 'data' represents all the stuff the 'GET' request got from url if the request was successful

### Question 5
In an AJAX POST request, what does the argument of the `.done()` callback - in the example below, that would be `data` - represent? (Hint: it's not the same as in Question 4.)

```
  $.ajax({
    url: 'http://ig-hacker-news.herokuapp.com/users',
    type: 'POST',
    dataType: 'JSON',
    data: { user: { name: "Anna", about: "instructor", email: "hi@gmail.com" } },
  })
  .done(function(data) {
    console.log("success!");
  });

-The argument 'data' represents the user info (name, about, and email) that is collected from user input if the post request was successful.

```
### Question 6
Suppose you had the following form in your HTML file. Use jQuery to write a single line of code that takes whatever the user entered in the textbox and saves it to the variable `user_input`.

```
  <form>
    <p>The dress is:</p><input type="text" id="color">
    <input type="submit" value="Submit" id="submit">
  </form>
```

  var user_input = $('#submit').val();


### Question 7
This code looks like it works, but when you run it, you see that the `UserApp.add_all_users()` function executes but `console.log` displays `undefined`. What's wrong with the code?

```
UserApp.get_all_users = function() {
  $.ajax({
    url: 'http://ig-hacker-news.herokuapp.com/users',
    type: 'GET',
  })
  .done(function(data) {
    console.log("success!")
  });
  UserApp.add_all_users(data);
};

UserApp.add_all_users = function(data) {
  console.log(data);
};
```

-The UserApp.add_all_users(data); should be within .done because that is where the argument data is being passed. Outside of that function, data no longer means anything.



