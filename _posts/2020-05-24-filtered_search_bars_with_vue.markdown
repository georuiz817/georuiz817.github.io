---
layout: post
title:      "Filtered Search Bars With Vue"
date:       2020-05-24 23:50:45 +0000
permalink:  filtered_search_bars_with_vue
---

When working with large amounts of data things can get messy quick. Most likely, you want your user to be able to see a list of all blog posts, recipes, images and be able to select one. But what happens when there's 100+ recipes? A user could endlessly scroll down to find the one they want, but it would be a lot easier for them to just search through them all! A user technically then would be able to "filter" through all of them based on key words, letters, numbers during their search. I had a similar situation in my Vue.js project and I'm going to show you a simple and easy solution with my own personal example. You might already have you data fetched and in its appropriate place and just need a search bar. For this example I'm going to do it from start to finish to make sure it is a fully understood process.

Note: In order to understand some of the concepts going further I'd suggest you already know basic Vue.js not all pieces of code are touched on and this is mainly to show how to get a quick search bar up. If you'd also like to see the search functionality that is being explained below, I suggest checking out http://horizons-library.herokuapp.com/#/fish
and messing with the search bar as you go along.
# 1.  Create your data
We will be displaying fish and hopefully getting to the point where we can search for a fish. So in our data object we will have a fish property as an empty array. We will also have a empty string property named search. While the fish array will hold all our fish data (empty for the time being). Search will hold the string we typed into our search bar. 

```
    data() {
        return{
            fish: [],
            search:  ' ',
        }
    },
```

# 2. GET your data
We want something in our fish array... Fish would probably be a good idea. Mentioned in previous blogs I've been working with ACHNI API so in this example I will be taking data from there. 

Here we use axios to GET the fish:

```
        axios.get('http://acnhapi.com/v1/fish/')
        .then(fish => {
            this.fish = fish.data
        })
```

If viewed in the console we will see the value of fish as:

```
{ {...}, {...}, {...}, {...} }
```

Something is a bit fishy though when viewed in the console.. It's not an array were taking in! It's actually an array like object. It's a large object that's values are also objects. You will see this a lot with JSON APIs.  Well we can't use important functions like filter, map etc on objects. We need to change that object to an array so we can filter through it. 

```
        .then(fish => {
				    axios.get('http://acnhapi.com/v1/fish/')
            this.fish = fish.data, //take in the array like object from the api
            this.fish = Object.keys(this.fish).map(i => this.fish[i]) //convert it to array of objects to use filter
            console.log(this.fish)//logged to make sure working correctly
        })
```

Now if viewed in the console we will see:

```
[ {...}, {...}, {...}, {...} ]
```


# 3. Filter through your array
Now that we have our fish and it's an array of fish objects, we can use a filter function to filter through our array. What we will do is make a function titled filteredFish. Then our function will filter through our fish array and return any fish name that matches our search property (that string we made earlier on that was going to hold whatever we put into the search bar).

Here is our filteredFish function:

```
    computed:{
        filteredFish: function(){
            return this.fish.filter((fish)=>{
                return fish.name['name-USen'].match(this.search.toLowerCase())
            });
        }
    }
```

# 4. Search bar in our template 
Everything we have made so far is not visible to our user. In this part we are going to make our actual search bar that a user can use and make our v-for directive to loop through all our fish. This front end uses Bootstrap Vue.

First we will make our input with our v-model of search to easily communicate and update our search property. 

```
<b-form-input  type='text' v-model='search' placeholder="search fish"></b-form-input>
```

Next we will use our v-for loop to loop through all the fish. We actually wil be looping through filteredFish and not our Fish array. This is because filtered fish is returning everything in the array with the added functionatlity of updating it upon search. Believes it or not, if nothing is in the search bar all fish will be displayed because all objects match empty string data. However, once you put in a specific name or letter, it's going to only show the objects that match.

Our v-for loop: 

```
        <div v-for="f in filteredFish" v-bind:key='f.id'>
            <b-card class="loopCard mx-auto mb-2">
                <router-link class="routerLink" :to="'/currentFish/' + f.id" >
                <b-card-title>{{f.name['name-USen'] | capitalize}}</b-card-title>
                <b-card-text>{{f.price}}<img width='10%' src='../../assets/bells_pic.png'></b-card-text>
                </router-link>
            </b-card>
        </div>
```

Wrapped up what all of this does it give you a search bar that when you type in key letters, will display the fish that matches the key letters instantly. It can be a bit confusing at first in regards to getting our data, converting json array like objects to actual arrays etc. But once you understand Vue basics the core thing I believe this blog will help you with is how to make a usable search bar. :)
