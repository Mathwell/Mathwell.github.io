---
layout: post
title:      "React/Redux Art Studio Website"
date:       2018-12-09 15:41:05 -0500
permalink:  react_redux_art_studio_website
---


For my final project I decided to make an art studio website.  The template I choose was clean a simple: white background, simple images and a minimum menu setting. 
![](https://farm5.staticflickr.com/4909/31337266297_7232df4525_b.jpg)

The main focus I put on a react/redux part of the project. First,  implemented router feature using react-router that allows easy navigation. Than created a store  - a place where all of the necessary data in our application lives. Any component can connect to it and pull the most recent data when needed. In the state of the store I keep the following information about artworks of the students: name, link on Flikr, description. 

From "Gallery" menu the user can manage the artwork data base. Artworks could be viewed, edited, added and delited from the database. 

Data percistence was implemented by connecting to Rails API Server. A very helpful resource I used  was this one [https://www.fullstackreact.com/articles/how-to-get-create-react-app-to-work-with-your-rails-api/](http://) . However, this resource only explains in details how to get data from API server and does not touch other requests.  I encountered several minor problems implementing POST, DELETE and PATCH requests. Luckely, the solutions were easy to find on developer resources.


