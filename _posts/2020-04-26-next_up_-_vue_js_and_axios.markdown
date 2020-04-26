---
layout: post
title:      "Next Up - Vue.js and Axios "
date:       2020-04-26 16:23:28 +0000
permalink:  next_up_-_vue_js_and_axios
---


I"ve decided to tackle a new tool. I've been seeing on a lot of job descriptions that Vue.js more and more is starting to become a required or at the most preferred library. Only knowing to my knowledge that is a fairly newer library for front end, I decided to go ahead and check it out. 

So far I'm very impressed on how it's been handling. It seems light-weight and fast compared to other tools. Also I have read in the past that once you know one component driven library, It's a bit easier to learn another. So going from React to Vue was a breeze. 

The project I've decided to do was a Animal Crossing library in where users can go and see quickly information about a item, villager, fish etc that they might be needing more information on. I quickly mapped out that I would be using GET requests for my index and show page for each category. Knowing I'd need a JSON/API I found http://acnhapi.com/ for the job. From there I was going to use fetch requests to grab the information needed. However, I was doing a bit of reading and my crash course on Vue both recommended Axios. Why? Well it's a pretty good JS library that really has one big thing over fetch requests.  You don't need to manually stringify the data when sending requests in axios, for fetch request you do. Although one small step it can get quickly confusing on where exactly it needs to go and when to use it. So better to remove it all together with Axios. 

An exampe of my component taking data from axios: 


```
import axios from 'axios'

export default {
    data() {
        return{
            fish: [],
        }
    },
		
    created(){
        axios.get('http://acnhapi.com/fish/')
        .then(fish => {
            this.fish = fish.data
        })
    },

```

Now if you're unfamiliar with Vue this could look a bit confusing but once broken down, all it really is a really simple component. Since most Flatiron students have learned React, and I'm coming from a React background I'll explain it in React terms for this example. But I do suggest learning Vue with all the correct tehcnical terms from a crash code course like the one I took over on Udemy. 

1. The fish:[], empy arry is our local state. It's currently set to empty upon the component being loaded. 
2. Once the component has been created. (think componentDidMount()) we start are axios request. 
3. Axios is grbabing information from the api with the route of fish. 
4. then once the request has been completed we will be taking our fish array (this.fish since we are trying to point to our component this is the key word here) and we will set it equal to the data recieved from the api. 

You can see here were not stringifying any data with:

```
  .then(response => response.json())   
```

This is just the very start of my project with Vue. Next I plan on implemented the show component. As well as using Bootstrap Vue to make sure the website is mobile reponsive. It's currently deployed over on heroku but theirs a whole lot of nothing on the site. I plan to fix that in the next upcoming days! 
