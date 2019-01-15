---
layout: post
title:      "React.JS Client with Ruby on Rails API. Stage 2: Design"
date:       2019-01-15 18:32:51 +0000
permalink:  react_js_client_with_ruby_on_rails_api_stage_2_design
---


![](https://farm5.staticflickr.com/4805/46702056202_ecdb4b70b3_z.jpg)

In a last post we’ve addressed the why. It’s time to address the how – the app architecture. How to get this app off the ground? What are all the components to bring the app to life?

I decided to use the following technologies for my web app:
   1.	React.js frontent for a quick load
          a.	All pages have access to a main menu to browse through pages: Home, About, Events, Books, Contact Us
          b.	All member can login using their credentials
          c.	Events will allow registered users to RSVP and place comments
          d.	Books will contain all books from past events and allow registered users to add reviews
          e.	Home and About are static informative pages 
           f.	Contact Us allows to send an internal message to bookclub team
   2.	Bootstrap/CSS for web design
          a.	Menu, thumbnails, pictures and other elements will be implemented using Bootstrap library and custom CSS
   3.	Rails API backend for CRUD 
          a.	Rails API will receive and sent data via JSON format
   4.	Postgres database for data persistence
          a.	Data will be stored in Postgres database. The format is chosen in consideration of future deployment on Heroku 
   5.	Heroku for deployment

*This is the stage to get technical. Developer or a team supposed to decide what major parts the application will consist of and choose a specific technology for each part. Based on that,  we can plan the development stage.  *

