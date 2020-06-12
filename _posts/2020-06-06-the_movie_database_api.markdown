---
layout: post
title:      "The Movie Database API"
date:       2020-06-06 17:00:23 -0400
permalink:  the_movie_database_api
---


APIs are beautiful things. When available, making calls to an API to access data versus having to go through the messy process of web scraping can speed up the data collection and cleaning process before your actual analysis begins. The data is usually already structured and there is often clear documentation outlining how to leverage APIs. [The Movie Database API documentation](https://developers.themoviedb.org/3/getting-started/introduction), for example, outlines the many types of data you can obtain from movie information to user account and review data. APIs can become even easier to utilize through the use of API wrappers. [tmdbsimple](https://github.com/celiao/tmdbsimple) is one such example of an API wrapper in python that allows us to make API calls through simple functions. Let’s take a look at how we can utilize tmdbsimple to obtain movie information.

To obtain movie information, we pass a movie ID through to produce a dictionary with basic movie details.  We can preview the keys in order to narrow down what we return. In this instance, we’re interested in the title, runtime and genres. Now, we know that the movie is *Frozen*, which was released in 2013 is 102 minutes long. *Frozen* can also be categorized as 3 genres: animation, adventure and family. 


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

But what if we don’t already have the movie IDs? We can actually search TMDB using the tmdbsimple wrapper. If we search for *Frozen*, we actually get multiple results. 


```
search = tmdb.Search()
response = search.movie(query='Frozen')
for m in search.results:
    print (m['title'])
```
Which returns: 

```
Frozen
Frozen II
Frozen
Olaf's Frozen Adventure
Frozen Fever
Frozen River
The Frozen Ground
Frozen
LEGO Frozen Northern Lights
Hope Frozen
Frozen in Love
A Frozen Christmas 2
Dawson City: Frozen Time
The Frozen North
Frozen Impact
The Frozen
Keep Frozen
The Frozen North
Howard Lovecraft & the Frozen Kingdom
A Frozen Christmas 3
```

Clearly, there have been multiple *Frozen* movies and related specials.[ Referring to the API documentation](https://developers.themoviedb.org/3/search/search-movies), we can pass some additional information to narrow our search. Adding the release year to our query, we cut down our results by about 75%. 

```
search = tmdb.Search()
response = search.movie(query='Frozen',year=2013)
for m in search.results:
    print (m['title'])
```

Which returns:

```
Frozen
The Frozen Ground
Pompeii: The Mystery of the People Frozen in Time
Frozen Silence
Jake and the Never Land Pirates: F-f-frozen Never Land and Little Stinkers 2013
100 Degrees Below Zero
```

While this isn't a perfect method, it certainly helps when we don't already have movie IDs. Furthermore, these results are ordered by best match so the first match will typically be what you're looking for. We can  
		
		





