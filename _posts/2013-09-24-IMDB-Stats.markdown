---
layout: post
title:  "Mining the IMDB Database - summary statistics"
date:   2013-09-24
categories: projects
---

This past spring I was in a data mining class and I spent some time working with
the [IMDB](http://www.imdb.com/) database. It is [freely available](http://www.imdb.com/interfaces), and
there are some [nifty tools](http://www.imdbpy.sourceforge.net/) for working
with it. The goal of my data mining project was to develop a decision tree or a
rule based classifier that could be used to predict a movies average user
rating based on its other attributes. So ideally, we would have a decision tree
that said something like "if a movie is made by Quentin Tarantino and stars
Brad Pitt, then it will have an average user rating of 9/10." Well the
decision tree turned out to be quite a bit more complicated and less insightful
then we were hoping, but in the process of building it we did come across some
interesting findings that this post is intended to summarize. 

<i>Note:</i> the data set was filtered to only include movies that meet the following
constraints:

* Produced in the US
* Genre isn't 'Short'
* Has at least 10 user ratings
* Released before 2013

### Genres ###
When building a rule-based classifier, rules similar to this kept showing up:

{% highlight ruby %}
if genre = 'Drama' then user_rating > 7
if genre = 'Horror' then user_rating < 5
{% endhighlight %}

This got us thinking that perhaps movies of certain genres just tend to be
better. The following table seems to support that idea.

<table>
 <tr><th>Genre</th><th>Average User Rating</th></tr>
 <tr><td>Documentary</td><td>6.3</td></tr>
 <tr><td>Animation</td><td>6.0</td></tr>
 <tr><td>Western</td><td>5.9</td></tr>
 <tr><td>Romance</td><td>5.9</td></tr>
 <tr><td>Drama</td><td>5.7</td></tr>
 <tr><td>Crime</td><td>5.7</td></tr>
 <tr><td>Mystery</td><td>5.7</td></tr>
 <tr><td>Adventure</td><td>5.6</td></tr>
 <tr><td>Family</td><td>5.5</td></tr>
 <tr><td>Comedy</td><td>5.5</td></tr>
 <tr><td>Fantasy</td><td>5.4</td></tr>
 <tr><td>Thriller</td><td>5.1</td></tr>
 <tr><td>Action</td><td>5.1</td></tr>
 <tr><td>Sci-Fi</td><td>4.9</td></tr>
 <tr><td>Horror</td><td>4.4</td></tr>
</table>

So it looks like either there are a lot of crappy horror movies out there, or
people just don't like horror movies as much as they like documentaries. It also
so happens that documentaries are on average the cheapest genre of movie to
produce, as the chart below shows.

<div align="center">
  <img src="/images/avg_budget_genre.png" width="90%"/>
</div>

Animation movies are also very popular, but their high cost is prohibitive. They
make up only 1% of the US movies in the IMDB database:

<div align="center">
  <img src="/images/percent_movies_genre.png" width="90%"/>
</div>

### MPAA ratings ###
One of the data attributes that lent itself really well to data mining was the
MPAA rating attribute. This attribute looked something like:

> Rated R for strong violence, language and some sexual content/nudity.

The reason these ratings worked so well for data mining was because the MPAA
likes to use certain keywords in their ratings: language, drugs, sex, violence,
and nudity. So the rating above could be broken down into to a series of
booleans indicating that the movie contained violence, language, sex and nudity,
but didn't contain any drugs. I was hoping to find some dirty statistic like
"movies with violence and drugs tend to be rated higher then those without," but
it turned out that MPAA ratings weren't a very good predictor of user ratings.
Actually, the presence of any of those keywords in a MPAA rating had a
slight negative correlation with the user rating attribute, instead of the
positive correlation I was expecting to find. 

So the MPAA ratings weren't very useful for predicting user ratings, but they
are still useful for looking at what kind of obscenities are filling our movies:

<div align="center">
  <img src="/images/mpaa_rating_reasons.png" width="50%"/>
</div>

We can also look at rating distributions:

<div align="center">
  <img src="/images/mpaa_ratings.png" width="45%"/>
</div>

And how rating distributions have changed over the past 20 years:

<div align="center">
  <img src="/images/mpaa_ratings_by_year.png" width="90%"/>
</div>
<div align="center">
  <img src="/images/mpaa_reasons_by_year.png" width="88%"/>
</div>

I was surprised that the percentage of 'R' rated movies being produced has
declined over the past 20 years. I wonder if the MPAA is just getting less
sensitive or if Hollywood is really becoming more PG as the chart above
suggests.

### Top Directors, Actors, and Actresses ###
While MPAA ratings and genres are interesting to look at, the real predictors of
how good a movie will be should be the people who made it. Here are some people
who consistently make great movies:

<i>Note:</i> Only includes directors with at least 3 movies, and actors or
actresses with at least 20 movies.

<table>
 <tr><th>Director</th><th>Average user rating</th><th>Number of movies<th></tr>
 <tr><td>Nolan, Christopher</td><td>8.41</td><td>7</td></tr>
 <tr><td>Unkrich, Lee</td><td>8.13</td><td>4</td></tr>
 <tr><td>Darabont, Frank</td><td>7.98</td><td>4</td></tr>
 <tr><td>Jackson, Peter</td><td>7.94</td><td>7</td></tr>
 <tr><td>Kubrick, Stanley</td><td>7.88</td><td>13</td></tr>
 <tr><td>Aronofsky, Darren</td><td>7.86</td><td>5</td></tr>
 <tr><td>Tarantino, Quentin</td><td>7.84</td><td>13</td></tr>
 <tr><td>Bird, Brad</td><td>7.83</td><td>4</td></tr>
 <tr><td>Wright, Edgar</td><td>7.78</td><td>4</td></tr>
 <tr><td>Vaughn, Matthew</td><td>7.77</td><td>3</td></tr>
 <tr><td>Fincher, David</td><td>7.76</td><td>9</td></tr>
 <tr><td>Affleck, Ben</td><td>7.73</td><td>3</td></tr>
 <tr><td>Ritchie, Guy</td><td>7.65</td><td>4</td></tr>
 <tr><td>Sharpsteen, Ben</td><td>7.65</td><td>4</td></tr>
</table>

<table>
 <tr><th>Name</th><th>Average user rating</th><th>Number of movies</th></tr>
 <tr><td>Hitchcock, Alfred</td><td>7.61</td><td>26</td></tr>
 <tr><td>Chaplin, Charles</td><td>7.33</td><td>30</td></tr>
 <tr><td>Serkis, Andy</td><td>7.27</td><td>20</td></tr>
 <tr><td>Lloyd, Harold</td><td>7.18</td><td>21</td></tr>
 <tr><td>Bale, Christian</td><td>7.11</td><td>28</td></tr>
 <tr><td>DiCaprio, Leonardo</td><td>7.10</td><td>27</td></tr>
 <tr><td>Parker, Trey</td><td>7.07</td><td>35</td></tr>
 <tr><td>Eckhardt, Oliver</td><td>7.00</td><td>25</td></tr>
 <tr><td>Rickman, Alan</td><td>6.98</td><td>32</td></tr>
 <tr><td>Norton, Edward</td><td>6.97</td><td>28</td></tr>
 <tr><td>Fishman, Duke</td><td>6.97</td><td>20</td></tr>
 <tr><td>Howard, Art</td><td>6.97</td><td>26</td></tr>
 <tr><td>Guinness, Alec</td><td>6.95</td><td>22</td></tr>
 <tr><td>Goelz, Dave</td><td>6.95</td><td>44</td></tr>
 <tr><td>Stone, Matt</td><td>6.95</td><td>23</td></tr>
</table>

<table>
 <tr><th>Name</th><th>Average user rating</th><th>Number of movies</th></tr>
 <tr><td>Bonham Carter, Helena</td><td>7.17</td><td>26</td></tr>
 <tr><td>Swanson, Gloria</td><td>7.08</td><td>29</td></tr>
 <tr><td>McGowan, Mickie</td><td>7.06</td><td>29</td></tr>
 <tr><td>Blanchett, Cate</td><td>7.06</td><td>29</td></tr>
 <tr><td>Bergman, Mary Kay</td><td>7.06</td><td>20</td></tr>
 <tr><td>Lynn, Sherry</td><td>7.03</td><td>32</td></tr>
 <tr><td>Cooper, Gladys</td><td>6.98</td><td>30</td></tr>
 <tr><td>Harlow, Jean</td><td>6.96</td><td>29</td></tr>
 <tr><td>Davies, Marion</td><td>6.95</td><td>41</td></tr>
 <tr><td>Dietrich, Marlene</td><td>6.95</td><td>33</td></tr>
 <tr><td>Hepburn, Audrey</td><td>6.94</td><td>21</td></tr>
 <tr><td>Plowright, Hilda</td><td>6.91</td><td>46</td></tr>
 <tr><td>Gale, Norah</td><td>6.90</td><td>20</td></tr>
 <tr><td>Winslet, Kate</td><td>6.89</td><td>21</td></tr>
 <tr><td>Michelson, Esther</td><td>6.88</td><td>23</td></tr>
</table>

Well that gives a quick snapshot of some of our findings. It would be cool to be
able to pinpoint the exact ingredients that make a great movie, but if that were
possible then making movies would be more of a science than an art.

