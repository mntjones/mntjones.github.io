---
layout: post
title:      "Rails Project: Childcare Calendar"
date:       2018-07-11 18:58:53 +0000
permalink:  rails_project_childcare_calendar
---


My Ruby on Rails Final Project is called Childcare Calendar (obviously, I have no marketing flair :). This app allows a user to create a job where they will need a caregiver. A caregiver will be able to see the open jobs and accept. 

## Setup
### Models

User Model  (Parent or Gaurdian) -
- has a name, password (secure), email, phone number, address, and num_of_kids

Sitter Model (Caregiver) - 
- has a name, password (secure), email, phone number,  and hourly_rate

Job - 
- has a start_date_time, end_date_time, user_id, and sitter_id
- has a method to calculate payment for the Sitter

### Controllers

**Application** has the root path, and shows the Welcome page with Sign Up and Log In capabilities for both User and Sitter.

**Sessions** has the login and logout paths for both User and Sitter. At the moment, it's not DRY as much of the logic is the same, but the redirect paths and the session creation are distinct.

**Users** has the creation of new Users and the display of the current users page. The show page only allows a User to view their jobs.

**Sitters** has the creation of new Sitters and the display of the current sitters page. The show page only allows a Sitter to view their jobs.

**Jobs** has the creation of new Jobs and displays the open jobs to the Sitters. Once an open job is claimed, it disappears from the open job page and shows up in the Sitter and User page.

## Using the App
Users:
A User would sign up or log in. They would then be redirected to their home page, which lists all of their jobs, open or claimed (past and upcoming). A User may also add a new job. If a job is open (unclaimed by a Sitter), the user may either update or delete it. A User can log out. 

Sitters:
A Sitter would sign up or log in. They would be directed to their home page, which lists all of their claimed jobs. A Sitter may also view a list of open jobs, and be allowed to claim them. Once claimed, the job would disappear from the open job page and appear on the Sitter's home page. A Sitter can log out.

## To be Implemented in V2
- A check to make sure the sitter is not double booked
- Allowed to update profile for both Sitter and User
- Show stats ?

## Challenges
One of my first challenges was figuring out the associations and which parameters belonged in which model. I began to code to get routes working, and changed things around to better suit my program. In the beginning, I had the address and phone numbers in the job model, but moved them to the User and Sitter models, as I felt they better belonged to those models.

Another big challenge was getting the new jobs to work properly. The first issue was being able to visualize how they were to be presented, and how to get them properly assigned and showing up on the individual show pages.

## Summary
This project has incorporated a lot of skills and programing logic. I feel more confident with routing and forms, and look forward to using this app for my own family! Overall, I am very pleased with this experience, as I felt it was both fun and challenging.

As I learn more and get more "professional," I'm going to need to improve presentation. I was able to do a little style with how things are presented, but no where near what a deployed web app would look like. I look forward to learning Javascript and incorporating that into my web apps. 
