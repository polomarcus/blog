---
title: "Analyze one year of radio station songs aired with SQL, Spark, Spotify, and Databricks"
draft: false
description: "One year of radio stations broadcasts were analyzed to notice their habits and if radio stations brainwashing is a thing"
tags : [
    "spark",
    "databricks",
    "SQL",
]
date: 2017-03-20T14:41:06+02:00
---
*Note: This post was originally published on [Medium](https://medium.com/@polomarcus/analyze-one-year-of-radio-station-songs-aired-with-sql-spark-spotify-and-databricks-835fcf73df6#.7o1uwd9vc)*

Whenever I drive or code, I listen to music, as this happens a lot, and in order to find new songs, I listen to the radio or I listen to Spotify's discover weekly playlist, *which made me like Mondays (because they release it every Monday)*

A french *old-school* institute called [MediamÃ©trie](http://www.mediametrie.fr/radio/) analyzes radio stations' songs. Since I have seen their study (*that I can't find anymore*) some years ago, I have been obsessed with creating my own.

![](https://cdn-images-1.medium.com/max/800/1*aic7vTL46SYNhhkdHgir9Q.png)
<center>*Mediametrie's image you can find online â†’ old school*</center>

This article will present the year 2016 for 4 main french radio stations through *fun* SQL queries, then we will connect each song to the Spotify API to create the radio stations' musical profile.

We will use the [Databricks community version](https://community.cloud.databricks.com/) to visualize our data. [All SQL queries and all results are available on this notebook.](https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/6937750999095841/1807085967979471/6197123402747553/latest.html) It's the “backstage” of this article, where the magic happens if we can say.

**Protip**: don't miss the bonuses at the end of the article

### Radio stations introduction

We all have a favorite radio station, mine is [Radio Nova](https://en.wikipedia.org/wiki/Radio_Nova_%28France%29) for their diversity, their humor, and as a hip hop fan this is the only national radio where we can hear *listenable* hip hop songs

![](https://cdn-images-1.medium.com/max/800/0*nKeR6DQGjRIQj5a7.png)

Radio nova had[ 1,4% of the audience in September 2016 (PDF to download from Mediametrie)](http://www.mediametrie.fr/radio/communiques/telecharger.php?f=b132ecc1609bfcf302615847c1caa69a).

![](https://cdn-images-1.medium.com/max/800/1*_g363O12zm0KugNa_qcQ0g.png)
<center>*Most 5 broadcasted songs on Nova in 2016*</center>

In order to see how a radio becomes number 1, we are also going to analyze the number 1 music radio called [NRJ ](http://www.nrj.fr/)who has 10,8% of the audience and 2 others : Virgin (5%) which, we'll see, sounds like NRJ, and Skyrock (6%), *don't mind the name it's a rap radio… haha*

![](https://cdn-images-1.medium.com/max/800/1*iKd8P0iu3oe6C_iOYeYeAA.png)
<center>*Most 5 broadcasted songs on NRJ in 2016*</center>

The main question is, after we compared these radios, should we give to Radio Nova the tips of how to be the number one based on NRJ's analyze? *What do you say, Nova? Learn from the best, right?!*

### Getting the Radio's songs data

![](https://cdn-images-1.medium.com/max/800/1*l8ljCalKR3Tpnpp9ZM9Kbg.png)
<center>*“What was this title?” Nova page*</center>

In order to extract the songs lists, artist, song title and timestamp, we are going to parse each Radio “What was this song?” HTML pages, except for Skyrock which [has a handy RESTful web service](http://skyrock.fm/api/v3/sound?search_date=2016-08-15&search_hour=04:59).

Every song extracted will be converted into this Song class to query them easily with (Spark) SQL:

```java
    Song(timestamp:Int, humanDate:Long, year:Int, month:Int, day:Int, hour:Int, minute: Int, artist:String, allArtists: String, title:String)
```
In 2016 300K broadcasts were collected:

* Nova : 95K broadcasts of 5000 different songs
* NRJ : 50K broadcasts of 800 different songs
* Virgin: 60K broacasts of 1200 different songs
* Skyrock: 100K broadcasts of 1000 different songs

Every songs is stored in a [parquet format](http://spark.apache.org/docs/latest/sql-programming-guide.html#parquet-files) to extract only once the data (*you're welcome radios servers :p*) and [to speed up SparkSQL queries](https://blog.cloudera.com/blog/2016/04/benchmarking-apache-parquet-the-allstate-experience/). *Btw, if you are interested by the file I can export it to you in CSV, or parquet.*

Remember that the best way to speed up, the [Spark doc](http://spark.apache.org/docs/latest/programming-guide.html#rdd-persistence) says often by more than 10x, queries, if you have to use the same SQL table (or Dataset/Dataframe) again and again, is to cache them in memory (*Thanks Databricks for the 6Go RAM server!*) with the `dataframe.cache()` method.

Let's dive into our analysis now ! 

### How many songs by day?
*Some days were not recorded by the radios' history system, so the real numbers should be a bit higher.*

![](https://cdn-images-1.medium.com/max/2000/1*0tYTwHCCN6r2nq6EqJojdA.png)
<center>*Songs broadcasted by day*</center>

Fun to see that both radio stations broadcast more songs during summer (if we do not take in consideration the one-week bug of Radio Nova, in blue, in August), this is certainly due to summer holidays. *They do a good job all year long, so, it's OK to take some days off, I guess!*

We can see that Skyrock and Nova broadcasts the same number of songs each day, whereas NRJ and Virgin a bit less, certainly due to more talk shows or untracked DJs night shows.

### How many different songs by day?
The real difference comes from the number of different songs played, see by yourself the number of different tracks per day:

![](https://cdn-images-1.medium.com/max/2000/1*Omx2QwvONBJMBLmUOtD5Pw.png)
<center>*Different songs by day*</center>

More mainstream radios such as NRJ, Virgin and Skyrock top 100/120 different songs a day whereas Nova is more about 280. If you want to discover more songs, it's clearly on Nova.

### How many different songs by month?

If we have a look to the monthly different songs, the gap between radios is even bigger.

![](https://cdn-images-1.medium.com/max/2000/1*7WL3--Hb00WNPvjeM5if8w.png)
<center>*Different songs by month in 2016*</center>

### Top 10 played titles by each radio station
It's interesting to see how “hits” are played through the year. 

We can notice summer hits: 
* [Kaytranada](https://open.spotify.com/track/0EM0yABJzbFOvZQkfvuvCy) for Nova 
* [Enrique Iglesias](https://open.spotify.com/track/6YZdkObH88npeKrrkb8Ggf) for NRJ
* [Kent Jones](https://open.spotify.com/track/27PmvZoffODNFW2p7ehZTQ) and [Drake](https://open.spotify.com/track/1xznGGDReH1oQq0xzbwXa3) for Skyrock 
* [Imany](https://open.spotify.com/track/1ZdWNpOXCJT1nmt40UuxWS) and [Kungs](https://open.spotify.com/track/0cAuqPI1R8RlFsXXWWO039) for Virgin.


We can tell that the most broadcasted songs are mostly aired during summer. So artists, play smart here and release your songs between February and June to have more chance to become number one, *or to have more people hating your music because they heard it too many times?*

#### Nova

![](https://cdn-images-1.medium.com/max/2000/1*9mum9beXiQln5uSyfy2yww.png)

#### NRJ

![](https://cdn-images-1.medium.com/max/2000/1*awiIMX1Bwu5rdS-_rkeeYg.png)

#### Skyrock

![](https://cdn-images-1.medium.com/max/2000/1*Z4KvMZzWL7ltwtjwMM5Nkw.png)

#### Virgin

![](https://cdn-images-1.medium.com/max/2000/1*nZMYiYJttXEOaV7KugtjHA.png)

### Percentage of music by day
If we take the average broadcasted songs by day and the mean duration of a song, 3.30 minutes, we can guess the percentage of music by day. The other percentage is likely to be talk shows, advertising or untracked songs.

![](https://cdn-images-1.medium.com/max/800/1*xAIRqQ96Leq1zSD--o4akA.png)
<center>*Percentage of music per day*</center>

To understand more these percentages, we should see what a normal day is for our analyzed radio stations.

### What is a typical Monday for our radio stations?

Let's have a look to the average of number of songs for all radio stations for Mondays

![](https://cdn-images-1.medium.com/max/2000/1*e3ev4GNUCtKPcnq9SmgoFA.png)
<center>*Average number of songs for Mondays*</center>

We can distinguish 2 gaps, during the morning and evening shows for every radio stations. *Amazing.* More seriously, no discovery here, it's a known fact that most radios have morning and evening shows during which there is less music and more talk.

#### Advertising time
If we recalculate the average percentage of music at noon, when there is no shows for all radio stations, we can estimate the percentage of advertising by radio by hour. We estimate that the radio hosts speak 5 minutes during the whole hour. *We have to note that radios may advertise more during prime time when they have a larger audience.*

For 60 minutes, we get from 7 minutes of advertising time, for Skyrock, to 15 minutes, for Virgin. In details, we have this table: 

![](https://cdn-images-1.medium.com/max/1000/1*VcuOm-luXT_e_q6d-5q9Zg.png)
<center>*Average minute of music and advertising for every Monday at noon*</center>

### Radios  brainwashing?
An annoying feeling we have sometimes with radios is we keep listening to the same songs over and over. As we are men and women who believe in science and not in our instinct we are going to use basic statistics to verify this weird feeling.

#### How many times is the same song aired on the same day?
![](https://cdn-images-1.medium.com/max/800/1*Ahz21it10spW3txOSnPJew.png)
<center>*Average number of times the same song isbroadcasted by day*</center>

These pie charts below tells us a lot about radio stations's habits, more mainstream radios such as Virgin, NRJ or Skyrock are more about to broadcasts the same songs multiple times.

![](https://cdn-images-1.medium.com/max/1000/1*t-xKlfHx8j5fWBSG5epeaw.png)
<center>*How many times the same song is broadcasted?*</center>

#### When is the next time we will listen to the same song during the same day?

![](https://cdn-images-1.medium.com/max/1000/1*S-baYaxkztVV7znKPKYRhQ.png)
<center>*Minimum difference in hours between the same songs broadcasted on same day*</center>

Again, the most mainstream radios, NRJ, Skyrock and Virgin tend to broadcast the same song most often 2/3 hours since it was first aired. Nova's value is more about 7/8 hours.

While we have different distribution, the average for our 4 radios is between 7 and 8 hours.

![](https://cdn-images-1.medium.com/max/800/1*Ve3UMz8tRiDVmVnca4vVUw.png)

#### How many new songs* are added and when?

*“New songs” means songs that are not yet broadcasted in 2016.

![](https://cdn-images-1.medium.com/max/2000/1*5PC0QuOvyDTStuoDK7zzXw.png)
<center>*New songs by month distribution*</center>

If we look at the average after April 2016, we see that's Nova is ahead, but don't forget Nova plays 2500 different songs each month, so it's normal statistically speaking

![](https://cdn-images-1.medium.com/max/800/1*NZfug_TEvZQhUR3zargkmA.png)
<center>*Average new songs by month*</center>

New songs are distributed equally along the week for all radios

![](https://cdn-images-1.medium.com/max/800/1*hwwdZoj1GRNnWuW7LokE7w.png)
<center>*New songs per weekday*</center>

### Common songs between radio stations

On the table below, we can see NRJ has 25% of common songs with Virgin and 12% with Skyrock. 

Virgin has 18% with NRJ while Skyrock has 9% of common songs with NRJ.

![](https://cdn-images-1.medium.com/max/2000/1*w1sB-Z8zzoP19Lsg2V-U8A.png)
<center>*Number of same songs broadcasted between radios*</center>

Nova has a few similar songs with the others radio, there are mostly legendary artists such as Bob Marley, Daft Punk, Aloe Blacc, Kavinsky, BeyoncÃ©… If you are interested by the full list look for the “Similar songs between radios” cell in [the “backstage” AKA the blog article's Databricks notebook](https://databricks-prod-cloudfront.cloud.databricks.com/public/4027ec902e239c93eaaa8714f173bcfc/6937750999095841/1807085967979471/6197123402747553/latest.html)

Our 4 radio stations are different, for sure, but do they have common songs between them? Surprisingly the answer is yes

* [Prince – Kiss](https://open.spotify.com/track/28S2K2KIvnZ9H6AyhRtenm)
* [C2C – Happy](https://open.spotify.com/track/255uSDEuvkWp1QyYnm82VJ)
* [Stromae – Formidable](https://open.spotify.com/track/4z70Px77quweOupQRiaG2Q)

I would classify these songs as songs that everybody likes, *you can play them at your party without any stress of being booed*

If we use a visualization for our previous table it will look like this, the blue bar is the similar songs, the orange and the green bar are the total of different songs.

![](https://cdn-images-1.medium.com/max/2000/1*XnAgFeqhykf0mhYurSKXJg.png)
<center>*Similar songs*</center>

### What are the secrets to be #1?

We have analyzed 4 radio stations based on the artist name, the title name and the day and time the songs were broadcasted. Beside letters and numbers, these 3 values mean nothing, if we want to make a deeper analyze we have to learn more about the songs played: how popular is the song right now? what is the genre of the song? How many followers does the artist have?

Hopefully, by connecting each song to the Spotify API we will get a lot of data we can play with :

> [https://api.spotify.com/v1/search?q=ARTISTTITLE&type=track&limit=1](https://api.spotify.com/v1/search?q=$encodedQuery&type=track&limit=1)

In 2016, we have collected 8000 different songs from the radios, so to get the artist, the track and the tracks' audio features from the Spotify API we have to make : 

> Number of songs x ([Artist](https://developer.spotify.com/web-api/console/get-artist/) + [track](https://developer.spotify.com/web-api/console/get-track/) + [audiofeatures](https://developer.spotify.com/web-api/console/get-audio-features-track/)) = 24K requests

![](https://cdn-images-1.medium.com/max/800/0*j0EeLA19ElJmN_ae.jpg)
<center>*From [HTTP STATUS DOGS](https://httpstatusdogs.com/)*</center>

That's a lot. Plus, Spotify has a limit of request in time, so we have got to do it slowly, 20 request every 2 seconds, *why not you know.*

BUT, with this slow rate one thing I didn't plan is we could see the number of followers change when we requested a song's artist, as most artists have multiple songs been broadcasted, the artist information was asked from twice to 10 times. *No problemo, right?* No…This will mess up our SQL join between artist and track data later just because the DISTINCT on artists information [were fake](https://www.youtube.com/watch?v=1IDF-8khS3w) due to `followers.total`

*I have to say this led me to craziness, because I had more songs after my join than before haha* 

![](https://cdn-images-1.medium.com/max/800/1*UlBp9dA-JJyY3aJ-klrsBg.png)
<center>*Spotify API Stats from
[https://developer.spotify.com/my-applications](https://developer.spotify.com/my-applications)*</center>

### Songs Popularity By Radio

#### Definition by Spotify

> The popularity is calculated by algorithm and is based, in the most part, on the total number of plays the track has had and how recent those plays are.

![](https://cdn-images-1.medium.com/max/2000/1*vVSuuElWOqbngrTlj4SNdw.png)
<center>*Percentage of songs popularity distribution by radio*</center>

No surprises here, mainstream radios NRJ, Virgin or Skyrock, tend to play more popular songs, *that's why I use the term mainstream, clever, right?*

![](https://cdn-images-1.medium.com/max/800/1*FwnhWdDxbYIQ_YhIjkLspA.png)
<center>*Popularity average*</center>

*But the real question is : was the song popular before it was broadcasted on the radio?*

### Audio features

The Spotify API gives [audio features extracted from the Song's soundwaves](https://developer.spotify.com/web-api/get-audio-features/#tablepress-215), thanks to these we can display a musical profile of each radio:

[In my opinion](https://www.youtube.com/watch?v=pWdd6_ZxX8c), the most meaningful audio features are :

* danceability *describes how suitable a track is for dancing based on a combination of musical elements including tempo, rhythm stability, beat strength, and overall regularity.*
* energy *is a measure from 0.0 to 1.0 and represents a perceptual measure of intensity and activity. Typically, energetic tracks feel fast, loud, and noisy.*
* valence *describes the musical positiveness conveyed by a track. Tracks with high valence sound more positive (e.g. happy, cheerful, euphoric), while tracks with low valence sound more negative (e.g. sad, depressed, angry).*

Let's see their average and their distribution, *as a average alone can be sometimes misleading*, among the radios' tracks. As Nova got more different songs than the others we are going use percentage to compare our radios to add more context to our stats.

[If you have read my Facebook Interview Journey,](https://medium.com/@polomarcus/my-facebook-interview-journey-5205e111155f#.r3w705wo3) you know this is where I failed during my SQL interview, this code is specially for you, dear Mr. Interviewer, no hard feelings though :p

```sql
SELECT ROUND( (COUNT(t.*) / subTotal.total_radio * 100),2) AS percentage_of_songs,
      subTotal.total_radio,
      ROUND(popularity / 10) * 10 AS popularity,
      t.radio
FROM AudioFeatureArtistTrackRadios t
JOIN (
    SELECT COUNT(*) AS total_radio, radio
    FROM AudioFeatureArtistTrackRadios
    GROUP BY radio
) AS subTotal
ON subTotal.radio = t.radio
GROUP BY subTotal.total_radio, ROUND(popularity / 10) * 10, t.radio
ORDER BY popularity
```
<center>*Brilliant SQL code*</center>

#### Energy

![](https://cdn-images-1.medium.com/max/2000/1*Y20xDfW6m6x4PQ-gdtMouA.png)
<center>*Energy by radio distribution*</center>

Mainstream radios tend to play more energetic songs, *I guess there are more easy to listen to?* Some example of song with a lot of energy are [We Are Your Friends -  JUSTICE](https://open.spotify.com/track/6Unf6X6PC7KZtrRXH3dFHg), [Steppin' stone - Davy Jones](https://open.spotify.com/track/7yI4qKGEFHNId1B893XopS), and of course, the classics from the classics [Jerk It Out – Caesars](https://open.spotify.com/track/1bx7OUl2UmAnA5oZkm9If7), I've first heard it while playing [SSX3 on GameCube](https://www.youtube.com/watch?v=-0x3aZEPcMA) 8)

![](https://cdn-images-1.medium.com/max/800/1*IySsIzTaReMzd1OZ9PxXWw.png)

#### Danceability

![](https://cdn-images-1.medium.com/max/2000/1*P4erZSV3quz3__oR2c24bA.png)

This chart tells us both radio broadcasts the same kind of danceable songs. Some example of danceable song are [Trick Me – Kelis](https://open.spotify.com/track/3aImJnJlAgcE7bJ1NxthGt), [Around the world – Daft Punk](https://open.spotify.com/track/1pKYYY0dkg23sQQXi0Q5zN) or [Anaconda – Nicki Mina](https://www.youtube.com/watch?v=LDZX4ooRsWs)

![](https://cdn-images-1.medium.com/max/800/1*JpPrbAzb0U13iMZK7PihXQ.png)
<center>*Danceability average*</center>

#### Valence / Positiveness

![](https://cdn-images-1.medium.com/max/2000/1*ujgMyDVxmhj2YlgfIM11HA.png)
<center>*Valence / Positiveness By Radio distribution*</center>

![]()

Same as the danceability, both radio broadcasts the same kind of positive tracks. Some examples : [September – Earth Wind & Fire](https://open.spotify.com/track/5nNmj1cLH3r4aA4XDJ2bgY),[Ska-Boo-Da-Ba – The Skatalites](https://open.spotify.com/track/4BLu47sbjr3aJZwxZujgXT) or [Hey Ya! – OutKast](https://open.spotify.com/track/5WQ1hIc5d2EVbRQ8qsj8Uh)

![](https://cdn-images-1.medium.com/max/800/1*Jaa8mmCC84LsxskMJjbuNg.png)
<center>*Valence / Positiveness average by radio*</center>


2 others interesting data, which are not Spotify ([Echo Nest](http://the.echonest.com/)) specific, are the BPM (beats per minute) and the songs duration

#### Tempo / Beats per minute

![](https://cdn-images-1.medium.com/max/2000/1*Xkq3Q3yjJaNowJkhzXP1FA.png)

#### Duration

![](https://cdn-images-1.medium.com/max/2000/1*67Kr4JwQOCrc2u6Obz3nMg.png)
<center>*Duration distribution*</center>

Nova seems to be a bit different from the other radios by playing shorter or longer tracks. Virgin, NRJ and Skyrock are really into 3-minute tracks.

When I first saw this graph, I couldn't help myself to think about this [Hocus Pocus' song called “Voyage immobile](https://open.spotify.com/track/1DhpyURGQ8gAQCYo8dOLQo)” (motionless journey) and this  sentence about our undiversified musical environment :

> “Je ne voyais que blocs longs de 3 minutes taillÃ© dans le roc et dans le mÃªme but”

> “I could only see 3-minute blocks from the same base with the same goal”
 
![](https://cdn-images-1.medium.com/max/800/1*fpld7Zi9lOJDPKWDdrcFpw.png)
<center>*The duration average in minute by radio*</center>

### Music genres

![](https://cdn-images-1.medium.com/max/1000/1*sgT6naW21Wu0M7sYaL2qMQ.png)

Spotify got some pretty weird music genres, have you noticed “post-teen pop”, “pop christmas”, *pop songs you listen during christmas I guess? haha*

We can clearly see that NRJ and Virgin, *which are very alike*, are more about pop/dance/electro music, their top 3 genres are : pop, dance pop and tropical house. Nova is about soul, funk and indie music, and Skyrock is more about rap, dance and pop

![](https://cdn-images-1.medium.com/max/800/1*_5E7highTXSqJ8rS7oFI0Q.png)
<center>*Number of different music genres by radio*</center>

#### Hip hop genres

![](https://cdn-images-1.medium.com/max/800/0*58-RGcDqjhx8XLD3.jpg)
<center>*First on rap*</center>

Skyrock is famous for its motto “1st on Rap”, let's compare Hip hop/Rap genres (genres with “rap”, “hip” or “hop” inside the name) with the others radios.

![](https://cdn-images-1.medium.com/max/800/1*OGs_m824iH2tMza0ziY8JQ.png)
<center>*Number of hip hop, rap songs by radio*</center>

OK, that's a close match between Skyrock and Nova, let's compare the internal hip hop genres now.

I don't really care about genres, but there are a lot of confusion between Hip hop, which is a culture, and rap, which is the actual fact of rapping, if you want to learn more check this [Wikipedia Chapter](https://en.wikipedia.org/wiki/Hip_hop#Culture), I also recommend the excellent [Netflix's documentary “Evolution of Hip Hop”](https://www.netflix.com/title/80141782)

![](https://cdn-images-1.medium.com/max/2000/1*AsTuELi8z5QUmnG25FfUmA.png)
<center>*Genres with Hip or Hop or Rap by Radios*</center>

Nova, in orange, is more about indie/alternative/undergroup hip hop music, and Skyrock, in blue, is really more into French rap/trap/hiphop and also popular rap. So let's fix Skyrock's motto by “1st on French rap” haha

### Music classifier for Radios' selection idea

[In my last article](https://medium.com/@polomarcus/music-recommendation-service-with-the-spotify-api-spark-mllib-and-databricks-7cde9b16d35d), I explained how to create your own music recommendation system thanks to these audio features.

A [fun project](https://en.coursera.org/learn/progfun1) (*the link is a tribute to the Scala Guru [Martin Odersky](https://medium.com/u/9a80872a98bb), he tends to say too many times that his Scala exercises are fun whereas they are brain melt haha*) would be to create an algorithm that will help music selectors to find radios style's songs.

#### Spotify recommendation system

Spotify's system is not only based on the  audio features we saw earlier. It also analyzes what others similar users listen to. This slide contains a [nice schema that explains their whole system.](http://www.slideshare.net/sinisalyh/scala-data-pipelines-spotify/5-Recommendation_systems)

### What's next?

Thanks to this project I have built solid foundations to query the Spotify API in Scala, process it thanks to Spark SQL, and visualize it thanks to Databricks. I think more projects are about to come, plus Spotify has just released, March 2017, this new endpoint [“Recently Played Tracks”](https://developer.spotify.com/news-stories/2017/03/01/new-endpoint-recently-played-tracks/) and ideas are coming.

### Databricks pros and cons

#### Pros

* Free community edition with 6Go RAM server
* Awesome and easy-to-use [Data Viz](https://docs.databricks.com/user-guide/visualizations/index.html)

#### Cons (or more, what can be better)

* Can only visualize a maximum of 10 elements when using a GROUP BY, the others elements go to one category called “Others”
* Not possible to choose the color of an entity, so a Radio can be blue on a graph and red on another, it can be sometimes confusing
* Cannot export graph as iframe, so we have to export pictures from the interactive graphs
* Cannot modify SQL on the Data Viz interface

### Thanks

- **Databricks**, for their awesome platform
- **Spotify**, for their easy-to-use API and their **human-readable** documentation
- [Radio Nova](http://www.novaplanet.com/) for being a top music [selecta](http://www.urbandictionary.com/define.php?term=selecta), I would not listen to the same music that I listen to today without you
- [Marc H'LIMI](https://twitter.com/m_hlimi), Radio Nova's advisor, for our exchanges
- Pierre Trussart, engineer and DJ, [Benjamin Thuillier](https://twitter.com/b_thuillier), scala rockstar, Nicolas Duforet, data science master, Justine Mouron, engineer
- My friends for hearing me talking about this project too often

### Bonus – Spotify Playlists
To thank for reading, I created 4 playlists of the most ~200 songs broadcasted sorted by the number of broadcast for :

* [Nova with Calipso Rose, Brisa RochÃ©, Kaytranada, The Roots, M.I.A, The Virgins…](https://open.spotify.com/user/cpolos/playlist/64DWZ46dFb50FaWs9eALIu)
* [Skyrock with Drake, Alonzo, Major Lazer, Timberlake, Soprano, PNL, Jul](https://open.spotify.com/user/cpolos/playlist/0x2SJgvfcBzxfiMTDkTuC4)…
* [Virgin with Imany, Twenty One Pilots, Sia, Kungs, Julian Perretta](https://open.spotify.com/user/cpolos/playlist/3ySBdFmKboUlMWfqSpLZio)…
* [NRJ with Enrique Iglesias, Soprano, Coldplay, Kungs, Amir, MHD, Tal](https://open.spotify.com/user/cpolos/playlist/7ECHPNZ5fjLggN2rg0poK3)…


