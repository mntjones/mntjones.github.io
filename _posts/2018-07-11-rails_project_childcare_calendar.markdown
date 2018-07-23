---
layout: post
title:      "Rails Project: Book Club"
date:       2018-07-11 14:58:53 -0400
permalink:  rails_project_childcare_calendar
---


My Ruby on Rails Final Project is called Book Club. This app is for people to review a book that was assigned to the club, see the other comments and the average rating of the book, see what the book of the month was. A User can also add a book to be read and reviewed, and edit and update their review for a previous book.

## Setup
### Models

User Model   -
- has a name, password (secure), email
- has many reviews
- has many books through reviews

Book
- has a title, author, number of pages, genre, month assigned and year assigned
- has methods to calculate average rating and review count
- has many reviews
- has many books through reviews

Review - 
- has comments and rating (1 - 5)
- belongs to User and Book


### Controllers and Routes

**Application** has the root path, and shows the Welcome page with Sign Up and Log In capabilities for the User

**Sessions** has the login and logout paths for the User. 

**Users** has the creation of new Users and the display of the current user's page, which lists their past reviews. 

**Books** has the creation of new Books and the display of the current book's page and list of books.

**Reviews** has the creation of new Reviews, editing/updating of past reviews and destroying reviews. Reviews are nested resources inside Users (edit/update/destroy) and Books (new/create).

## Using the App

A User would sign up or log in through the Welcome page. They would then be redirected to their home page, which lists the books they've reviewed, with their comments. The User has an option to edit or delete each individual review. Each book title is a link to the Book page, where a user can view all of the comments made about the book and see the average rating. At the end of the user home page, they also have an option to view the list of books or to log out.

The list of Books has all of the information about all of the books. At the end of the page, a user has the option to go back to the user home page, or to add a new book. Each book title is a link to the individual book page.

On the book home page (for each title), a user has the option to add a review. If they have previously reviewed the book, a user would then be redirected to the edit page and allowed to update their previous review. On this page, a user can also redirect to the Book list or the user home page.

## Challenges
One of my challenges was determining what actions were going to be available on which pages. I moved things around a lot to try to get a logical flow to the pages.

Another challenge is determining which validations I needed and to make sure they worked as expected. An example is that I need the rating of the book to be from 1-5. I misused the wording to do this check, and suddenly my reviews were no longer saving. Another difficult validation was the year assigned for the Book model. I wanted to make sure that is was a 4 digit year, beginning with 19 or 20. I was able to do some web searching to help with the regex, and check terms. One validation that I did not include, but will at a later time, is the check for proper email format.

## Summary
This project has incorporated a lot of skills and programing logic. I feel more confident with routing and forms, and look forward to using this app! Overall, I am very pleased with this experience, as I felt it was both fun and challenging. I got some experience with some app presentation skills, such as using the "fields with errors" to show users why their form submittal failed.

As I learn more and get more "professional," I'm going to need to improve presentation. I was able to do a little style with how things are presented, but no where near what a deployed web app would look like. I look forward to learning Javascript and incorporating that into my web apps. 
