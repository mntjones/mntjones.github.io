---
layout: post
title:      "Book Club - now with Javascript!"
date:       2018-10-16 09:52:20 +0000
permalink:  book_club_-_now_with_javascript
---


For my portfolio project for the Javascript/AJAX section of my web developer's career track, I am adding Javascript/AJAX functionality to my Rails project.

### Requirements
Some of the requirements for this project are:

1. Must render at least one index page (index resource - 'list of things') via JavaScript and an Active Model Serialization JSON Backend.

Book Index uses the ActiveModelSerializer to render JSON. My list of books has a "More Info" button to get more than the title, author and month/year assigned. Each book loads the info with the individual book.

2. Must render at least one show page (show resource - 'one specific thing') via JavaScript and an Active Model Serialization JSON Backend.

Book Show uses the ActiveModelSerializer to render JSON. The show page loads the reviews for the individual book.

3. Your Rails application must dynamically render on the page at least one 'has-many' relationship through JSON using JavaScript.

My Book object "has_many" reviews, which are rendered on the index and show pages.

4. Must use your Rails application and JavaScript to render a form for creating a resource that submits dynamically.

My New Book form submits dynamically using AJAX.

5. Must translate the JSON responses into JavaScript Model Objects using either ES6 class or constructor syntax. The Model Objects must have at least one method on the prototype. Formatters work really well for this.

In book.js, I have a JavaScript Model Object constructor and a prototype method to showReviews.


### Setting up

To set up the new features of my Rails app, I worked on the backend first. I changed my controller's actions to render JSON and and set up my ActiveModelSerializers for my Book model.

I created a book.js file to put all my javascript in. In the file, I had my javascript book class, which included a constructor and my moreInfo() function. I also used a prototype function - showReviews(), to meet project requirements. Finally, I included the button action functions in this file as well.

### Challenges

I got my data to render JSON, but it wasn't showing up on the webpage correctly - just a JSON object. Also, my nested objects were not rendering properly.

To fix this, I had to find the correct data being sent and set the constuctor attributes correctly. Instead of just data.title, I needed to use data.attributes.title.

I also had a hard time getting the "more data" in my index to show up in the correct spot on the page - all of the "more info" was showing up under the first listed book. To correct this, I had to create a container that used the book.id to set up the position, and call that container id in the button click javascript function.


### Project Summary

I found this project challenging, but not as difficult as other projects. Since we were just adding new capability to an existing project, I already knew how the project should function, so that was a big part of it. Trying to get the data to show up where I wanted it to show up, was the hardest part. Overall, I'm pleased with what I was able to do with this project.
