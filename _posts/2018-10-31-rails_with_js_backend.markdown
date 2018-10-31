---
layout: post
title:      "Rails with JS Backend "
date:       2018-10-31 14:46:48 +0000
permalink:  rails_with_js_backend
---


The next step of improving my Home Health Scheduler Application was to add backend feature through Java Script and JSON API. 

I used Active Model Serialization for creating custom JSON data for three related models: Nurses, Patients and Visits. A very few changes in the corresponding controllers allowed to handle both format requests: HTML and JSON. 

My improved and extended application now allowes to browse through nurses and visits details, see scheduled visits for nurses and add new visits dynamically  without rerendering a page. This addition gives the application a new power of accessing to the information. It is now more intuitive, fast, convenient and easier to analyse.

Backend Java Script code is logically separated into corresponding files that can be plug-in page or controller specifically or as a whole bulk depending on application specifics. 

My code could be found [here](https://github.com/Mathwell/HHC-Scheduler-Rails-with-JS).
