---
layout: post
title: "ICYMI: KDD Conference (Tuesday)"
permalink: icymi-kdd-conference-tuesday
tags: [icymi, events, talks, links, conferences]
comments: true
---

### Today's schedule

**Tue, 8/15**  
07:00-08:00: KDD breakfast   
07:00-08:00: Keynote: Bin Yu - Three Principles of Data Science: Predictability, Stability, and Computability   
10:00-12:00: Recruiting
12:00-13:30: KDD Women's Lunch     
16:00-16:30: China Chapter Meeting: Intelligent Dispatch Systems at Didi Chuxing    
16:30-17:00: China Chapter Meeting: Data Science and AI Practice in China Industry: Some Personal Experience   
17:00-18:00: Deep Learning    
16:30-late: KDD 2017 Banquet   

-----

#### [Keynote: Bin Yu - Three Principles of Data Science: Predictability, Stability, and Computability](http://www.kdd.org/kdd2017/keynotes/view/three-principles-of-data-science-predictability-stability-and-computability)   

Prof Bin Yu is one of the remarkable people in the field who are able to see the big ideas that endure across different fields and from past to present anad articulate them well. Some key takeaways:    
* Computing was borne out of necessity for use in statistics for the census, yet the two fields have diverged since then. With data science what we're seeing is a re-merging of the two fields  
* Predictability, stability and computability are the three principles of data science: Prediction is the central tasks with computation as its core; good prediction implicitly assumes stability between past and future. Stability (relative to data and model perturbations) is also a minimum requirement for interpretability and reproducibility of data driven results    
* Stability refers to stability relative to appropriate data perturbations (e.g. bootstrap, subsampling, adding small amount of noise to data) or model perturbations (lasso/ridge models, different models of deep learning)    

<p align="center">***</p>

#### KDD Women's Lunch

The incredible and badass panel of this year's 3 keynote speakers Prof Bin Yu, Prof Renée J. Miller and Prof Cynthia Dwork shared their personal experiences and great stories about working in the field before taking questions.

[Katy Yam](https://www.linkedin.com/in/katyyam) stood up and passionately gave some advice on negotiation, with others in the room chipping in. A few points from that plus talking to Katy and others in a smaller group after the event for salary negotiation (or just general negotiation) that I remember:    
* ALWAYS ASK. Keep asking. From her experience, she sees men ask 10 times for every one time a woman asks for a salary raise    
* Do your research before you ask for a salary raise  
* Shop around in the job market to understand your market value. Have a counter-offer at hand   
* Don't feel bad about asking for what you want. Think about how you are pulling up the women behind you -- if you settle, you might be held up as an exaxmple for why the next woman can't get what she's asking for. One person gave the example of how not just her but the whole department got salary increments after she asked for better compensation   
* Instead of being the first to put forward your idea, especially when you are the lone voice for that viewpoint in the room, hang back, listen, then summarize the viewpoints of everyone else before putting forward your point        
* Find a way to get the person you are negotiating with to say yes before you put forward your request. E.g. "Here's the project I'm planning, does it sound good? And here are the resources we need, do you agree with it? Oh and relatedly I'd like a raise. :)". Even if you ask a question that elicits a "no" response, what you can do is to summarize what the other party says about it, and ask if that is right, and if summarized well you should get a "yes"   
* A psychological trick: Start nodding while talking and the other party might subconsciously start to nod along   
* Give others time to digest by saying: "You don't have to answer now, but xxx, and we can discuss this again tomorrow." Some people need time to digest and your strategy might backfire if you insist on an decision immediately   

Also learnt that [Prof Jennifer Neville](https://twitter.com/ProfJenNeville) is the force behind the female representation and the women's lunch event -- MAJOR PROPS!!

<p align="center">***</p>

#### Intelligent Dispatch at Didi

Some stats: 20+ million trips a day, 400 million riders, 17.5 million drivers, with services ranging from P2P ridesharing to designated driving to car rental to bikesharing     

Some problems and solutions:   
* Dispatch of trip request from rider to driver: Bipartite graph match: Hungarian matching algorithm (Kuhn-Munkres algorithm), which is globally optimal, optimizing for travel time at first but later taking into account for future information on supply and demand  
* Comprehensive resource allocation approach, e.g. for a DiDi Premier (higher tier) driver that is dispatched to a DiDi Express (lower tier): Reinforcement learning   
* Estimation of the service score for each driver to improve rider exxperience  

Talk was unfortunately (but not surprisingly!) very surface-level.

<p align="center">***</p>

#### China Chapter Meeting: Data Science and AI Practice in China Industry: Some Personal Experience   

* Challenges with enabling traditional industry with AI: 1) Data is not systematically collected and data quality is poor 2) Sophisticated, non-standardized application scenarios 3) Traditional techniques may not lend themselves easily to the AI framework => AI+ or +AI?  
* +AI: Identifying a specific problem, e.g. packing things in a warehouse, and applying AI to improve over the current approach   
* AI+: Providing end-to-end AI solutions, i.e. AI-as-a-service, e.g. search service, graph computing and analysis service  
* Next step: How do we maintain the services as the number of users and types of applications grow?   
