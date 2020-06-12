---
layout: post
title:      "The Movie Database API"
date:       2020-06-06 17:00:23 -0400
permalink:  the_movie_database_api
---


	APIs are beautiful things. When available, making calls to an API to access data versus having to go through the messy process of web scraping can speed up the data collection and cleaning process before your actual analysis begins. The data is usually already structured and there is often clear documentation outlining how to leverage APIs. The Movie Database API documentation, for example, outlines the many types of data you can obtain from movie information to user account and review data. APIs can become even easier to utilize through the use of API wrappers. tmdbsimple is one such example of an API wrapper in python that allows us to make API calls through simple functions. Let’s take a look at how we can leverage tmdbsimple to obtain movie information.
	To obtain movie information, we pass a movie ID through to produce a dictionary with basic movie details.  We can preview the keys in order to get
	
```	
identity = tmdb.Movies(109445)
response = identity.info()
response.keys()
```
