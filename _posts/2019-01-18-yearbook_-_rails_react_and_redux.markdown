---
layout: post
title:      "Yearbook - Rails, React and Redux"
date:       2019-01-18 18:43:09 -0500
permalink:  yearbook_-_rails_react_and_redux
---


I have successfully added Javascript and jQuery to my Rails application...now what? The next pieces to layer onto my continuous learning are the React  framework and the Redux container. For my final project, I was tasked with marrying a front end React and Redux App with a backend Rails App.

## App Description

I decided to make a yearbook app, where you can add photos of people with their name, age and a personal motto. This was designed to show a CRUD application with the use of React.

## Rails

The Rails portion of this application has a single model (Member) that has attributes of :name, :age, :img_url, and :motto.

The MembersController has the basic CRUD methods.

The new part with Rails in this project is connecting the routes and server up to play nicely with the frontend. I ran into some problems with configuring CORS, but once I got that working, the Rails part was pretty simple. I used the following for setup: https://www.fullstackreact.com/articles/how-to-get-create-react-app-to-work-with-your-rails-api/

## React

One of the requirements for this project was to use ``create-react-app``. This was new for me and there are several ways to incorporate the backend and front end, but essentially you have two separate projects.

Some of the big issues for me with the React side of things was figuring out what components I needed and how I wanted things to be displayed. I used the React dev tools to help me understand what the props and state were, and to help debug when the connections weren't working. 

In my project, I have a MemberCard that displays the attributes of each member and a MemberForm that allows you to add a new member to your yearbook.

## Redux
The Redux used for this project closely followed the lessons that I've had from Flatiron school. The one strange thing I did run across was that the createStore didn't want more than two items in it, so I had to combine my redux dev tool line with the applyMiddleware using composeEnhancer.

## Conclusion

Overall, this was a positive experience for me. As it wraps up my time with Flatiron school, I am pleased with what I've been able to accomplish in such a short time and I am looking forward to the challenges in my future.


