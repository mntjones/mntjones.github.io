---
layout: post
title:      "Oh CRUD! - Sinatra and ActiveRecord"
date:       2018-05-10 21:37:57 +0000
permalink:  oh_crud_-_sinatra_and_activerecord
---


This week I learned how to pull it all together using Sinatra, ActiveRecord, SQLite, and Ruby. The project is a simple blog that is made up of Post objects that are persisted to a database.

The first step is to set up your Gemfile to require Sinatra, ActiveRecord, Rake, SQLite and any other gems that make testing and compiling your project easy and understandable. Update your Rakefile and config.ru file. The environment file needs to have code to connect the database.
```
configure :development do
  set :database, 'sqlite3:db/<database-name>.db'
end
```

Set up your database and use ActiveRecord::Migration structure to set up your table. 

Create your class Post file, inheriting from ActiveRecord::Base. This will give access to all of the Create/Read/Update/Delete (CRUD) methods for your Post objects.

### Create

Set up an erb file to display (GET) a form to submit the attributes of your object (in this case, two text fields - name and content). Once the form is submitted, code inside your controller's POST action extracts the attributes and creates an object from ActiveRecord to both instantiate and save to your database. 

### Read

You can have several different Read files depending on what information you want to show. For our Posts example, we can show all Posts using `GET '/posts' `or a specific Post using `GET '/posts/:id'` where the id attribute is assigned when a Post is created and added to the database. If a user enters looks under 'www.something.com/posts/3', then the route sets the id =3. Using the .find_by method from ActiveRecord to set your instance variable, you can then show the instance variable object attributes.

### Update

To edit a post, set up a route that renders your form with the previous information - `GET '/posts/:id/edit'`. When the form is submitted, a PATCH action is sent to `PATCH '/posts/:id`. This controller action will update the information and save to the database. This line must also be added to your form `<input id="hidden" type="hidden" name="_method" value="patch">`. Your config.ru file must also contain the following lines so that ActiveRecord::MethodOverride intercepts the form  and sets the value to 'patch.' 
`use Rack::MethodOverride
run ApplicationController`

### Delete

The delete action is actually just a button that shows up on a view page. Similar to the update action, an extra line needs to be added to your form,  `<input id="hidden" type="hidden" name="_method" value="DELETE">` , with the value of delete instead of patch.

These lessons with Sinatra and ActiveRecord are pulling together how a web application comes together and how all the parts work together behind the scenes.



