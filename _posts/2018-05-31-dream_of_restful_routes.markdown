---
layout: post
title:      "Dream of RESTful Routes "
date:       2018-05-31 00:43:52 -0400
permalink:  dream_of_restful_routes
---


The REST uses the HTTP Protocol to communicate information about your session on a web site. This includes any CRUD actions that need to be persisted after moving away from a page. REST stands for Representational State Transfer and refers to a set of guidelines for HTML verb + URL combinations and their designated actions. The main REST terms are:

1. Create - POST
2. Read - GET
3. Update - PUT/PATCH  (replace/modify)
4. Delete - DELETE

Following the conventions of REST makes it easier for others to understand  and follow your code due to standarization. It also allows you to use the already determined routes and methods for your application.

### Create

To Create a new instance of a model and save it to a database, two routes are used. 

(1 - new)The first is to GET the information from a user => ` get '/model/new' ` renders a form to collect information required to instantiate a model. When a user submits the form, the <form> action lays out the POST route.

(2 - create) The second is to POST the collected information to create an instance of the model and persist to the database => ` post '/model' `. The code to create the model and instance and save to database is in this route.

### Read

To Read your webpages, you use the ` get ` command to render a webpage. The main read routes are (3 - index) show all and (4 - show) show singular.

### Update

There are two different update commands available - PUT and PATCH. The difference between these is that PUT will completely replace all fields of your data and PATCH allows you to update pieces of your data. To use these commands, you need to use an  input line that is hidden when your edit page (5 - edit) `get '/model/:id/edit`' is rendered `<input  id="hidden" type="hidden"   name="_method"    value="patch">`. This tells the form to override the method that is set to POST in the form opener and instead PATCH. In your controller action (6 - update) `patch '/model/:id' ` should be code to update any parameters that have changed.

### Delete

Delete is very straightforward. A user would go to a single instance of their model and run the .destroy method on that instance. This removes the instance from the database. The controller action (7 - delete) is `delete '/model/:id/delete' ` . The delete action is triggered by a form, but this form does not have any parameters to save. This input line should be added to your form: `<input id="hidden" type="hidden" name="_method" value="delete">` is a manner similar to the update commands.


Hopefully, this post helps to clarify the relationship between CRUD and REST. Following these conventions will help you get your website up and functional quickly. Good luck and happy coding!



