---
layout: post
title:      "What is 'Self' and Do I Have a Complex?"
date:       2018-03-02 05:16:16 +0000
permalink:  what_is_self_and_do_i_have_a_complex
---


My coding odyssey has brought my to the wonderous land of Object Oriented Programming. In Ruby, we started learning about what a Class is and all the basics that bring an Object to life. A Class is a group to which an Object can belong to. Classes have attributes and methods that are shared by its Objects.

This concept is not too hard to understand. Take, for example, a Book Class. Objects in a book class will have an author, a title, and a number of pages. These are common attributes for all books. Methods could include turn_page and remove_from_shelf.

Even the differences between local variables (owned by a method), instance variables (owned by an instance of the class), and class variables (owned by the class, available to all instances of the class) seemed to make sense. I thought I was cruising through this module. 

And then I hit 'self.'  

'Self' in Ruby refers to an Object - but what that Object is changes. Yet there is always only one 'self' at any point - the current Object or default Object you're working with.

Instance vs Class methods were really what made my head explode. When do I use 'self' and what does it mean to use it?

Class methods: 'self' for a class method  is the Object whose method it is. (owns)

Instance methods: 'self' references an instance of the Object. (uses)

This example from http://www.railstips.org/blog/archives/2009/05/11/class-and-instance-methods-in-ruby/ is brilliant in its simplicity and clarity.

class Foo
  def self.bar
    puts 'class method'
  end
  
  def baz
    puts 'instance method'
  end
end

#Class Object
Foo.bar # => "class method"
Foo.baz # => NoMethodError: undefined method ‘baz’ for Foo:Class

#Instance of an Object
Foo.new.baz # => instance method
Foo.new.bar # => NoMethodError: undefined method ‘bar’ for #<Foo:0x1e820>
