---
layout: post
title:      "React-Redux Portfolio Project"
date:       2019-11-09 21:11:16 +0000
permalink:  react-redux_portfolio_project
---

My final projcect has finally come to an end. Well, actually the whole course has! It has come a bitter-sweet end. I've never been one for schooling.. So being able to accomplish such a difficult task of completing the course and balance school / work-life has been very rewarding. What really helped me get through this final stretch was the React-Redux curriculum course. 

React-Redux project (and that thunk thing) - 

My final project taks was to complete a React-Redux front end w/ a Rails API back end project. My idea was Gobbler. Gobbler would give users the ability to create a dish (object) with a few attributes main, sides and a drink. It would be then put into our React-Redux state and sent to our api for safe keeping. 

Having already a great understanding of Rails the setup for this was fairly quick and easy. Just a simple scaffold with a single object did the trick. Then for extra flair just a couple of validations. We then got rack-cors up and running with our * so it'll white list anything. When working with a single object and having no associations, you can get your back end up in running in mere mins. 

Now for the fun part part which is our React-Redux. At this point React is mainly just our visual front end side and UI. We needed 5 statless componenets but I think I had a great deal more. I had a footer, nav, home page, errors page etc. You'd think 5 is alot but once you actually start making a project you realize how little that actually is. They were the easiest to make b/c well they had 0 state. It was all presentational. 

I did have a few containers that did have state within them and connected to our redux-reudcers. Users can create, view all, view, and delete a dish. These were all very important and were required for the project. The trickiest part of these was the thunk. 

Thunk: A great tool and interesting to use. However, with that being said I wish there was more of it on the course. We spent ALOT of time working on how to make a project without it. Then at the very end with only 1 readme and a lab we were given it and required to have it on our project. I remebred trying to implement a delete function and struggling b/c we learned delete in our course, but not with thunk. 

Overall I believe my project went great and i'm excited to present. I hope I can continue to add on to it and even get it up and running on postgres. As for now I just used sqlite b/c my computer is a bit...slow and I didn't want complicate anything. :) 
