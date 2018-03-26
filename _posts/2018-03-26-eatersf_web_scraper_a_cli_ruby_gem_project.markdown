---
layout: post
title:      "EaterSF Web Scraper: a CLI Ruby Gem Project "
date:       2018-03-26 16:06:35 +0000
permalink:  eatersf_web_scraper_a_cli_ruby_gem_project
---


This blog post focuses on how I created my Ruby Gem - an Eater SF web scraper.

The first step was to Google how to make a Ruby Gem. I used Bundler (http://bundler.io/v1.12/guides/creating_gem.html) and followed the steps to get a skeleton of the files I would need to get a working Gem.

Next, I used the Ruby Gem guide (http://guides.rubygems.org/make-your-own-gem/) to fill out the gemspec and install it.

## Coding
The next part is to write code. I did this incrementally, checking to make sure one part nominally worked before moving on to the next part. First, I followed this video walkthrough: https://www.youtube.com/watch?v=_lDExWIhYKI .

This helped me set up my dependencies and lay out how I wanted my classes to interact. My app is structured like this: CLI -> Restaurant -> Scraper. This helped me figure out what each class needed to do and how they would be used. I started with my CLI and built out the general welcome and list_restaurant methods. Then I built my restaurant class. Initially, I had my scraper methods in the restaurant class, but determined that is made a lot more sense to make a scraper class to do all the work.

My CLI file had three main components - a welcome method, a list_restaurant method, and a blurb method. The welcome method welcomes the user and asks for the initial choice - the heatmap or the essentials map. The method then calls the list_restaurant method and show the list for the appropriate choice. After the list is shown, the blurb method is called and asks the user for the number of the restaurant they would like more info on, or to list or exit. If a restaurant is chosen, the information - including address, phone and description - is displayed. The CLI continues asking about restaurants until list or exit is entered. Exit leaves the app.

My Restaurant file does only one thing - it constructs restaurant objects. There is a class array that holds the restaurant objects, and the initialize method that constructs the objects from an array of hashes provided by the scraper class.

The Scraper class was the most difficult due to the way the webpage was constructed. I'll talk to the difficulties in the next section. The scraper class has a method for each restaurant property - name, address, phone number, and description blurb. There is also a method to put all the properties into an array of hashes, which is used by the restaurant class.

## Difficulties
By far, the hardest part was scraping the webpage. The name part was relatively straightforward, but the phone, address, and blurb all had  Sponsorship ads that needed to be identified and weeded out. Then I had to deal with missing data - one of the restaurants didn't have a phone number. The address and phone number were under the same tags, so I had to separate them out. Some of the solutions I came up with feel 'hacky,' but since I must work with what is there, I'm not sure how to make it better.

There were other issues as well, including setting up my working environment so I could run files correctly. I had to install Homebrew and rbenv to deal with my permissions issues. I had to re-setup my github ssh keys. Dealing with these types of difficulties made me very comfortable with searching for help on the internet and working with the terminal.

## Final Thoughts
This was an excellent project. I was worried about the lack of guidelines and how to get started, but the provided video made things clearer and I get the real value in learning how to organize a project. The freedom in how to set things up was liberating, as well. There were a couple times where I scrapped my method of handling data and came up with something simpler.

I look forward to the review and learning even more about how to code smartly and efficiently.


