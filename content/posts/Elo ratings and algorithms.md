+++ 
draft = false 
date = 2023-02-01T10:21:07+02:00
title = "Elo rating and algorithms"
description = ""
slug = ""
authors = []
tags = []
categories = ["Computer Science"]
externalLink = ""
disableComments = true
math = true
series = []
+++
# A reasonable question... 
So you won, you won a 27 move game with an extraordinary checkmate, your opponent is devastated, your ego is inflating and your elo is rising. Elo? Who made up that weird name? Why is your rating system called like that? If you are thinking these questions, all I can say is that I was in the same place as you. Turns out, Elo was a real person, Elo or Arpad Emmerich Elo was a Hungarian-American physics professor with a soft spot for chess, like you and me. He created the elo rating system that replaced the Harkness rating system that was used from 1950 to 1960, his system is now used in chess federations around the world including the famous FIDE federation. But why would I randomly start talking about a rating system? Because my dear reader, a rating system is nothing but an algorithm and do you know who is good with algorithms? Computers ofcourse. so let's dive in. 


![](/images/elo.jpg)

*Big brain Arpad (left) with some random dude*

# Math part 
I think we talked enough history and it's now time to get to the math part. But before we go there I need to explain that different versions of the elo rating system are used around the world and not Elo's original principals. That leads us to examine two of the major rating systems out there, the  alogrithm of 400 and USCF's K-factor. 
### Algorithm of 400
The algorithm of 400 is used by several organizations around the world and is a personal favorite. It goes like this: 
- For each win, add your opponent's rating plus 400
- For each loss, add your opponent's rating minus 400
- And divide this sum by the number of played games

$$ Performance\\ rating  = \frac{Total\\ of\\ opponent's\\ rating + 400 * (Wins - Losses)}{Games} $$

##### Example: 
Let's say that I played against a player with 500 elo (yes, I am still at that level) and I won. 
$$Performace\\ rating = \frac{500 + 400 * (1)}{1}=900$$

Alright, now that we understood the simple math behind it, we can move on the the code part, because it would be unfair if we didn't get to write some code. 

##### Code: 
I am gonna use Python for this example: 

```
    #This program will implement the algorithm of 400
    rating = 500 + 400 * 1 / 1 
    print(rating)

    #result: 900.0
```
Dead simple right? Great, let's move on to the K-factor. 

### K-factor 
And now, introducting, USCF's algorithm used along with their custom classification of players. The k-factor can be estimated by dividing 800 by the effective number of games a player's rating is based on plus the number of games the player completed in a tournament. 
$$\Nu e = The\\ number\\ of\\ games\\ a\\ player's\\ rating\\ is\\ based\\ on.$$
$$m = The\\ number\\ of\\ games\\ a\\ player\\ completed\\ in\\ a\\ tournament.$$
$$\Kappa = \frac{800}{\Nu e + m}$$

##### Example: 
Let's say that I am a chess player that plays in a tournament and I have completed 10 games, my rating is based on 40 games. That results to: 
$$Player's\\ rating = \frac{800}{40 + 10} = 16$$

##### Code: 
Again writing this snippet with Python: 
```
    #This program implements the K-factor algoritm 
    rating = 800 / (40 + 10)
    print(rating)

    #result 16.0
```
Once again, nothing fancy. 

# Epilogue 
In conclusion the field of chess rating's is diverse with lots of algorithms and variations of them, but I hope that this article unclouded your vision and sparked a flame of curiosity about the subject. In the coming days or months I might do an article about the vast field of IQ rating systems, because yes that is a reality, so stay tuned on this site.

# Sources: 
https://en.wikipedia.org/wiki/Elo_rating_system

https://www.cantorsparadise.com/the-mathematics-of-elo-ratings-b6bfc9ca1dba

https://en.wikipedia.org/wiki/Arpad_Elo

