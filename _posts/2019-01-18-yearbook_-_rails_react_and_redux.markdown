---
layout: post
title:      "Yearbook - Rails, React and Redux"
date:       2019-01-18 23:43:08 +0000
permalink:  yearbook_-_rails_react_and_redux
---


I have successfully added Javascript and jQuery to my Rails application...now what? The next pieces to layer onto my continuous learning are the React  framework and the Redux container. For my final project, I was tasked with marrying a front end React and Redux App with a backend Rails App.

## App Description

I decided to make a yearbook app, where you can add photos of people with their name, age and a personal motto. This was designed to show a CRUD application with the use of React.

## Rails

The Rails portion of this application has a single model (Member) that has attributes of :name, :age, :img_url, and :motto.

The MembersController has the basic CRUD methods.

The new part with Rails in this project is connecting the routes and server up to play nicely with the frontend. I ran into some problems with configuring CORS, but once I got that working, the Rails part was pretty simple. I used the following for setup: 


