---
layout: post
title: "ICYMI: Machine Learning in Matching & Marketplaces @ Airbnb"
permalink: icymi-machine-learning-in-matching-and-marketplaces
tags: [icymi, events, talks, links]
comments: true
---

### Overview

**Event**: [Machine Learning in Matching & Marketplaces](https://www.eventbrite.com/e/airbnb-tech-talk-machine-learning-in-matching-marketplaces-tickets-36229705023)  
**Date**: 2017-08-01  
**Venue**: Airbnb HQ, San Francisco  
**Overall**: Good mix of related yet different talks, major props for getting together speakers from 3 companies (must not have been easy to coordinate!). Having 4 talks + Q&A in 2h limited the depth of each talk and the Q&A though; I used to be of the camp that having a good variety of shorter talks is better as it appeals to a broader swathe of people and interests, but starting to lean towards the model of having just one or two talks that go into more detail ([Instacart's meetup](https://www.meetup.com/SF-Bayarea-Machine-Learning/events/239380972/) earlier this year was a great example).

-----

### Talk by talk

<p class="message">
  <b>Disclaimer</b>: Think of this as my projection of the 4d experience on a 2d space with some amount of non-random noise -- I tried my best to capture the essence of each talk but there might be some loss of fidelity!
</p>

#### Machine Learning in Airbnb Pricing Strategy by Jieying Chen and Julian Qian

**Motivation**: Hosts might not be well-equipped to set optimal prices for their listings, so Airbnb suggests prices for each night to optimize bookings and revenue. A guest booking model gives the probability of a guest booking a night on a listing, while a pricing strategy model then comes up with the suggested price to charge for each night on a listing. This talk focuses on the latter. Challenges include: having limited observations of price changes, unique listings (one listing not comparable to the next), price-dependent features and expensive ground truth (e.g. if Airbnb suggests steeply discounted prices, hosts might not neccessary want to take these suggestions).

**Solution**: A regression under hinge loss is used, because if a listing is booked, it implies that the suggested price is less than or equal to the optimal price and vice versa.

<p align="center">***</p>

#### Online Learning for Dynamic Pricing at Lyft by Ashivni Shekhawat

**Motivation**: Prices have to be dynamic for a consistent service level (in terms of ETA) as demand and supply fluctuate. Volatility in demand can be hard to predict. Take a look at how price sensitivity spikes just before the hour as riders rush to meet their appointments in the plot below!

![Plot of price sensitivity throughout the day]({{ site.url }}/assets/2017-08-01-icymi-airbnb-talk-lyft.jpg "Plot of price sensitivity throughout the day")

**Solution**: A model trained on historical data gives baseline predictions of prices, while real-time online learning provides additional adjustments to those prices.

<p align="center">***</p>

#### Personalize Facebook News Feed with User Content Profiler by Meihong Wang

**Motivation**: There is huge diversity in users and content; how then do you rank content in the Facebook news feed?

**Solution**: They combine the probability scores of various outcomes -- liking a post, commenting on post, watching a video etc. Many features are used, including feed interaction history features, story type coefficient features (that indicate type of content), global counter features (not sure what these are), other coefficient features (that have to do with social interaction). They use both an entity-based approach, which requires post content understanding and user topic modelling (here they note that the right level of granularity and a lot of good and accurate data are important), as well as an embedding based approach. The latter starts with non-content features like user demographic data, the current post content and historical post content. The current and historical post content goes through a text process (unigram/bigram). There is also history pooling for historical post content. All of these then go into a neural net.

![Facebook]({{ site.url }}/assets/2017-08-01-icymi-airbnb-talk-facebook.jpg "Facebook")

<p align="center">***</p>

#### Rich Context in Airbnb Search Ranking by Hui Duan and Tao Xu

**Motivation**: Airbnb search ranking is challenging because 1) there is no absolute relevance (heterogenous inventory and user preference), 2) the sequential nature of a user's decision-making process (a user typically makes a number of searches and later searches tend to be highly filtered with little heterogeneity in the listings) and 3) it is a two-sided market (guests and hosts).

**Solution**: The first step is to use log data to attribute outcomes and assign empirical utilities: positive (booked), small (viewed but didn't book), negative (booked but rejected). There was a point about needing to sample the data carefully because of how a user's decision-making process worked, but I missed that.The next step is the ranking model. They started off using something called [LambdaRank](https://medium.com/@nikhilbd/intuitive-explanation-of-learning-to-rank-and-ranknet-lambdarank-and-lambdamart-fe1e17fac418), which weights the top position more so that the most relevant result would float to the top (e.g. you are more likely to have the 2 best results ranked in 1st and 10th place, as opposed to 3rd and 6th place). When they tested it, what they found was that guests booked and contacted the hosts more, but host acceptance dropped. Turns out it is also important to push poor results to the bottom as well. They then tweaked LambdaRank to use a dual discount curve for the loss function (see picture below). Lessons learnt: 1) build data carefully (careful label attribution and data selection) and 2) formulate your model to closely emulate the real world.

![Airbnb]({{ site.url }}/assets/2017-08-01-icymi-airbnb-talk-airbnb.jpg "Airbnb")

-----

### Closing thoughts

One question I wanted to ask, but didn't get the chance to (because public speaking of any sort terrifies me and we were down to the last question by the time I was done rehearsing my question in my head for the tenth time), was: 

> I noticed some of the speakers are data scientists, some machine learning engineers, some software engineers. Could you take turns to talk about the distinction between and interaction among the different roles in your respective companies that work on data science/machine learning?

Honestly, I think an ethnographic study of the data science community done through a round of internships in various tech companies could make for a pretty interesting PhD. Just credit me in your acknowledgements and let me read your thesis if you do this. ;) 