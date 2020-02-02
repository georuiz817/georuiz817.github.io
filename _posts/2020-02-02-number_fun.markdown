---
layout: post
title:      "Number Fun"
date:       2020-02-02 16:26:59 -0500
permalink:  number_fun
---

Wanting to focus on another project and keep my skills up to date, I decided to tackle React Hooks. Being less than a year old I thought it would be something new and interesting to try and would also look good during any interviews, projects etc.  We didn't get to learn it through Flatiron due to the cirriclum not being updated with it. So I figured i'd better learn it independetly. 

The project I decided to make is called Nuber Fun, the premise was to try and guess the number the computer was thinking of by inserting it into a form. 

Now to use hooks with this I wanted two state objects, the human number and the computer number. In order to win the two state objects would have to be === to each other. 

I personally think it's simplier to hook into the state rather than build a constructor etc. It also makes it easier to not have to call this.state.humnum etc.. 

The human number would be inserted into the input bar and the computer number would be randomized by three different categories easy 1-10, normal 1-50, and hard 1-100. The game would be defaulted to easy with useEffect which is basically a componentDidMount. Now when it comes to useEffect, i'm not sure if it's any easier than using componentdidMount or other life cycles. Yes it consolidates them into one method. But in order to use it properly you'll need to know how to manipulate that the method using an array or another method. So hindsight to me it just feels like it would be easier to quickly right componentDidMount. 

A challenge a come across in this was actually the CSS. Depdning on your guess, if you got it right, what difficulty you're using etc all depending on colors, placement, things popping up etc. So I really needed to make sure everything was aligned properly and had a old timey video game feel to it. 

Overall I enjoyed messing around with hooks. This is only a basic project but it's a good start and based off my research and project I'd be happy to tell any potential interviewer I've had some type of introduction to hooks. 
