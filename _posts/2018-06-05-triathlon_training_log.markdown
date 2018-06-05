---
layout: post
title:      "Triathlon Training Log"
date:       2018-06-05 16:23:52 +0000
permalink:  triathlon_training_log
---

## My Sinatra Portfolio Project MVP

For my Sinatra Portfolio Project, I decided to create a Triathlon Training Log. The models will be a User and a Log item. 

*  User has_many logs
*  User can signup
*  User can login
*  User can logout

 While logged in:
*  User can create a log
*  User can view a list of logs
*  User can view a single log
*  User can edit a single log
*  User can delete a log

 A Log belongs_to a User. An exmple of a Log entry is  
>  Date: YYYY/MM/DD
>  Swim Distance (meters): XX 
>  Bike Distance (kilometers): XX 
>  Run Distance (kilometers): XX 

### Setup
I used Corneal (https://thebrianemory.github.io/corneal/) to create the skeleton of my Sinatra App. This gem creates the required files and adds in a lot of the interdependency code. To complete, I needed to add one other gem to my Gemfile (rack-flash) and add `use UsersController` and `use LogsController` to my config.ru Now that I had my file structure set up and my model ideation complete, I began to fill in the code.

### Database and Models
The database files included a Users table and a Logs table. The User has a username, password_digest, and email. The Log has a date, swim_distance, bike_distance, run_distance, and user_id. I also created seed instances to help with debugging.

Using this database setup, I created my models. The Log belongs_to a User. The User has_many Logs, and has_secure_password, and validates username and email.

### Views
I separated out the views into users and logs. The default '/' route is included in the Application Controller, and has the Welcome message and a choice to either sign up or log in. 

The users views include signup, which included fields for username, email and password, and login, which is a person's username and password only. 

The logs views include the CRUD routes - new (create), show and list (read), and edit (update). A delete/destroy option is included in the show view.

Create - the new_log file is a form that asks for a date and at least one of three activities to be filled in. If either a date is missing, or all three activities are blank, an error message will appear, the form will not be saved, and you will remain on the new_log page.

Read - the log_list and show_log files display different views of the logs. After a create, edit, or delete, a user is directed to one of these pages.

Update - the edit_log page is accessible from the show_log. The edit form updates a previous entry, and has the same rules for blank data as the create form.

Delete - the delete button is accessible from the show_log. This button deletes the current log and redirects to the log_list. A success message should appear on the list to confirm deletion.

### Controllers
I have a separate controller for the users and logs, and they both inherit from the application_controller. 

The application_controller has the route for the initial '/' route and the helpers - `logged_in?` and `current_user`.

The users_controller has routes for signin (GET and POST),  login (GET and POST) and logout (GET).  Sessions are enabled and session_secret is set. There is logic in the controller that checks if you are `logged_in?` and if so, takes you straight to the log_list if there is an attempt to get to the signup or login page. Logout is accessible from the log_list and destroys a user's session and redirects to the login page.

The logs_controller has routes for logs (GET), new log (GET and POST), show log (GET), edit log (GET and PATCH) and delete log (DELETE). Rack-flash has been required to display error/success messages, as required. The logic deals with making sure that the person viewing the logs only has access to their logs and cannot read, edit or delete any other user's logs.  There is also logic to make sure that the information provided in the forms is adequate to create or edit an object instrance.

### Summary
This project was exciting in that I created a functioning web app that behaves like other web apps that I've used before (albeit, less pretty). There were many lessons learned in working with databases, checking for sessions, and displaying and saving the correct information. I feel more confident in my debugging (and Googling) skills and am beginning to feel like a real programmer! My TriTraining app can be found here: https://github.com/mntjones/tritraining  
