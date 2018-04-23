---
layout: post
title:      "Progamming with 'Magic'"
date:       2018-04-23 01:51:13 +0000
permalink:  progamming_with_magic
---


This week I learned to code with ActiveRecord and discovered some pros and cons with coding with 'magic.' Upon completing my object oriented Ruby section, I learned about SQL and how to use databases to keep information organized in tables, and accessible outside of a singular programming session. Importantly, I learned how to take Objects in Ruby, and save the information and relations into a database - to use ORM (object relational mapping).

One of the gems used to do this is ActiveRecord. From http://guides.rubyonrails.org/active_record_basics.html - 
"Active Record is the M in MVC - the model - which is the layer of the system responsible for representing business data and logic. Active Record facilitates the creation and use of business objects whose data requires persistent storage to a database. It is an implementation of the Active Record pattern which itself is a description of an Object Relational Mapping system."

ActiveRecord makes the relationships between Ruby Objects seemless with the "belongs_to" and "has_many" designations. There are also built in methods that allows ActiveRecord to manipulate data using CRUD - Create, Read, Update, and Delete.

While using ActiveRecord makes coding easier, it does make figuring out errors more unclear. To debug your code, it is helpful to turn on the SQL debug logging so you can see what is happening behind the scene (https://til.codes/how-to-turn-on-sql-debug-logging-for-activerecord/).

Overall, when using complex relational models, ActiveRecord can help keep your code clean and help make the data models clear. 
