---
title: Static Site Search
date: 2018-06-01 11:00:13 -0400

---
Over the summer we will be transition several sites to Hugo Static Site Generator and Forestry Content Management System. While static sites are fast and have many benefits, they lack the dynamic functionality of a back-end server. This makes Search, Contact Forms, Ajax Controls, etc. Difficult to implement. Forestry recommends a SaaS called Algolia to handle Search, but it makes more sense for our purposes to use an open source solution. I have been looking into Lunr.js, ElasticSearch, ElasticLunr, and others, but this site uses Grav's Search.

The idea behind Static Site Searching is index the entire site, render it in a JSON file, Search the JSON File, Find where the search tokens exist, and then navigate to that part of the site. This means that the user has to receive the JSON file before any search can be performed. This can be a problem with larger sites, because the more there is to index, the larger the JSON file.

A common approach to minimizing the size of the index file is to eliminate words that are so common that they aren't useful for searching. Does anyone really need a listing of every page containing, "the?"
