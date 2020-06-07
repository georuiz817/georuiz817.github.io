---
layout: post
title:      "Technical challenge and how I tried to stand out"
date:       2020-06-07 17:14:13 +0000
permalink:  technical_challenge_and_how_i_tried_to_stand_out
---


Technical challenges can be hard especially because you never know what you're going to get. You can end up having to solve a problem over zoom in front of another developer, you can have a take home project that can range from solving a simple problem to creating a whole project, or you can even just have a technical talk where you're asked a series of questions. Regardless, theirs tons of ways you can stand out especially when it comes to take home projects. 

Recently I was tasked with completing a take home project that didn't seem that hard. However, if it's not that hard that means everyone who's taking it most likely it able to solve it. In order to stand out I had to make sure my project was not only visually great but elevated in other ways. 

# The project
The task at hand was to use JavaScript to create an array of location objects and then display their properties on the front end. Theirs a ton of ways of doing this but most importantly the bare minimum to do is: 

1. Define/Create an array with some made up values for locations 
2. Create a function to map through the array with the desired properties shown
3. Use an event to trigger the function in HTML

examples: https://www.w3schools.com/jsref/jsref_map.asp

I took this a bit further to stand out. Heres how: 
# Used a JS framework
Instead of using vanilla HTML,CSS, and JS which most developers can do or at least figure out, I decided to go with a framework. Using a framework in my thought process still was applicable due to it being JavaScript and also showed I had the ability to understand components among other things. I decided to use Vue.js due to it being easy and light weight. 

# Third party API 
I could have just created an array of random information and mapped through that. However, I thought it would be more interesting to GET data form a third party. Not only would it be accurate data but it would help show I have the ability to do so. I used Axios to obtain data from a third party weather API.

Still have my array of locations but instead of manually setting the value I used Axios to request data and then store it in the locations array:


```
import axios from 'axios'
export default {
  name: 'weatherComp',
  data() {
        return{
          locations: [],
        }
    },
  created(){
     axios.get('http://api.openweathermap.org/data/2.5/group?id=524901,703448,2643743&units=metric&appid=   REMOVED API KEY')
        .then(locations => {
            this.locations = locations.data
        })
    },
}
```

# Made it more visually appealing 
Finally for displaying the information. You could just have the information in a list that is displayed with no color, mobile responsiveness etc. However, I wanted to take it on step further by making the component visually appealing. I went ahead and used Bootstrap to make each location be stored in a mobile responsive card with color. It was just an extra way to show I have the ability to make things visual and use another tool like Bootstrap. 

```
<template>
  <div class='weather-comp-body'>
    <div v-for="location in locations.list" v-bind:key='location.id'>
      <b-card class="text-center bg-secondary text-light">
        <b-card-title>{{location.name}}</b-card-title>
        <b-card-text> Unix date/time: {{location.dt}}</b-card-text>
        <b-card-text>Weather: {{location.main.temp}}°C</b-card-text>
      </b-card>
    </div>
  </div>
</template>
```

Coming across challenges theirs going to be easy ones and hard ones. This one was particularly on the easy side. However, it wouldn't of been enough for me to do the bare minimum listed above. Sure it would have been completed and maybe someone would have liked it. However, going further with all the steps listed showed I had the ability to not just go ahead and Google how to map through an array, but use a set up/build a project with a framework, manage components, make requests with Axios, and use Bootstrap and make a website mobile responsive. For such a small project if you look at the big picture you can see theirs way more to it then just showing the weather. Which is why you should always strive to go above and beyond in a technical project. It doesn't hurt! Don't worry about over doing a project. Theirs no over doing, why would a company not want you to show off all your skills, they're trying to hire and pay you! 




