---
layout: post
title:      "The Movie Database API"
date:       2020-06-06 17:00:23 -0400
permalink:  the_movie_database_api
---


APIs are beautiful things. When available, making calls to an API to access data versus having to go through the messy process of web scraping can speed up the data collection and cleaning process before your actual analysis begins. The data is usually already structured and there is often clear documentation outlining how to leverage APIs. The Movie Database API documentation, for example, outlines the many types of data you can obtain from movie information to user account and review data. APIs can become even easier to utilize through the use of API wrappers. tmdbsimple is one such example of an API wrapper in python that allows us to make API calls through simple functions. Let’s take a look at how we can utilize tmdbsimple to obtain movie information.

To obtain movie information, we pass a movie ID through to produce a dictionary with basic movie details.  We can preview the keys in order to narrow down what we return. In this instance, we’re interested in the title, runtime and genres. Now, we know that the movie is Frozen, which was released in 2013 is 102 minutes long. Frozen can also be categorized as 3 genres: animation, adventure and family. 


```
identity = tmdb.Movies(109445)
response = identity.info()
response.keys()
```

Which returns: 

```
dict_keys(['adult', 'backdrop_path', 'belongs_to_collection', 'budget', 'genres', 'homepage', 'id', 'imdb_id', 'original_language', 'original_title', 'overview', 'popularity', 'poster_path', 'production_companies', 'production_countries', 'release_date', 'revenue', 'runtime', 'spoken_languages', 'status', 'tagline', 'title', 'video', 'vote_average', 'vote_count'])
```

```
identity = tmdb.Movies(109445)
response = identity.info()
response['title'],response['release_date'],response['runtime'],response['genres']
```

Which returns:

```
('Frozen',
 '2013-11-27',
 102,
 [{'id': 16, 'name': 'Animation'},
  {'id': 12, 'name': 'Adventure'},
  {'id': 10751, 'name': 'Family'}])
```




