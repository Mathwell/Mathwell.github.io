---
layout: post
title:      " NPI Lookup Scraper Gem"
date:       2017-12-29 23:09:50 -0500
permalink:  npi_lookup_scraper_gem
---


Gem is a very convenient standardized way to extend a ruby program functionality.  Gems are automatically downloaded and installed, by simply including them in the list in Gemfile.  What makes them very powerful is that any programmer could create a gem and make it accessible to everyone. Thus, gems are a community tool of communication, sharing and, supporting.
All gems have the same structure. This makes them easy to code and easy to decode. Each gem has a name, version, and platform. Inside the gem are the following components. code, documentation and gemspec.
To create my gem I used “bundle gem” command. This automatically created a structure of the new gem with all necessary folders and files and conveniently commented instructions where to fill with my code.
For my gem project I choose to create a scrapper for NPI Lookup website – a free National NPI number registry. NPI - National Provider Identifier – is is a unique 10-digit identification number issued to health care providers in the United States by the Centers for Medicare and Medicaid Services (CMS). My choice of the website is related to my current job position as an intake coordinator in home health care agency. NPI Lookup is a routine screening done multiple times daily.  It looks natural to automate this process to be able to pull up necessary information that matches search criteria in a form of an object that could be used to autofill fields in multiple electronic forms and documents that are used in Home Health Care.

To implement my idea I used: 
 - Nokogiri Gem as an HTML parser for raw data from website
- OO Model for creating Provider’s object  and fill it in with data
- CLI model for a command line controller


As a result NPI Lookup Scraper Gem is able to extract data from http://www.npinumberlookup.org/ in a form of a list and get to further details when element from a list is chosen by an order number or a name.

Please find my  my   NPI Lookup Scraper Gem [here.](https://github.com/Mathwell/NPI-Lookup-Scraper)

