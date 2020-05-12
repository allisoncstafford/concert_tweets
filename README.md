# concert_tweets
Extracting information on concert performances from tweets.

## data source
Cheng-Caverlee-Lee September 2009 - January 2010 Twitter
Scrape: https://archive.org/details/twitter_cikm_2010

## task
Extract information about concert appearances of
musicians, performers or bands.

### relevant tweet examples
Sending pics of Alice Cooper concert I saw Monday Night. It was absolutely fantastic.
He Rocks
Last chance 2-for-1 Concert for Hope tickets to Miley, Jesse, Demi concert
tomorrow! Pls RT!
Jeremy sings with the La Jolla Country Day Madrigals tonight at the winter concert—
Yay! #fb
Latest YouTube info Alicia Keys holds YouTube concert for World AIDS Day - The Daily
...: Fresh off her appearance ...

### goal
Extract who was the performer, when and where
was the show, the Twitter user who attended it, and the sentiment of the tweet. Not all
of these fields are available in all tweets, and that’s ok. For example, for the first tweet
above, the result should be:
{ who: “Alice Cooper”, when: “2009-10-26”, where: null, audience: “54434622”,
sentiment: “positive” }
And for the fourth tweet above, the result should be:
{ who: “Alicia Keys”, when: “2009-12-01 “, where: “YouTube”, audience: null, sentiment:
“neutral” }

### note
Each row in the dataset includes the user id who sent the tweet, as well as the
timestamp for the tweet. For the ‘when’ field, we are interested in the date of the show
(not just the tweet). We are not interested in any other tweets, including tweets about
performers which don’t mention concerts. For example, these tweets are not relevant:

hasn't tweeeteddd in HELLA long! I'm back and loving the new Alicia Keys
Trackhttp://bit.ly/SBpkp
I don't wanna wait anymore to see the video of #LadyGaga - #BadRomance
@britneyspears I love so so much your new video "3"
Hello twitter, I just woke up. I'm breakfasting. A long day wait me.

## solution
This repo has three parts: 
1. a classifier to determine relevant tweets,
2. an entity recognition algorithm that extracts the information, and
3. a short ppt explaining the approach and results.