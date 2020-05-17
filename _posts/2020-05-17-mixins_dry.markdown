---
layout: post
title:      "MIXINS = DRY"
date:       2020-05-17 10:20:52 -0400
permalink:  mixins_dry
---

When making our code we want to adhere by the don't repeat yourself rule (DRY). As I go about a project I realize very quickly when something like a function,  a state object, or even CSS is being re-used multiple times in different classes and components. Before getting to work on exactly how to clean up the code, I continue the project as usual and take a note of everything I'm noticing. I then at the end of the day go back and find a way to make those more DRY.  One great quick way is to use mixins. According to the official Vue.js website, the definition of Mixins are "Mixins are a flexible way to distribute reusable functionalities for Vue components. A mixin object can contain any component options. When a component uses a mixin, all options in the mixin will be "mixed" into the component's own options.". 

Vue mixins are very similar to Sass mixins as they have a similar use. You're able to keep code DRY and use the mixin functions in different areas. If you haven't seen Sass or used Sass mixins I'd suggest https://www.w3schools.com/sass/sass_mixin_include.asp. Just as quick introduction to mixins, in Sass you'd define the mixin and then be able to use it in any style rule. It's extremely helpful when having blocks of CSS that you're going to be using multiple times. For example: 

```
@mixin color-theme {
          color: blue;
				  background-color: red;
				  border: 5px solid;
          padding: 5px;
          box-shadow: 5px 10px #888888;
}

h1 {
  @include color-theme;
}
```

The mixin is defined at the top with all its values. It can then be passed on by including. In this case all the code in the color-theme rule is being mixed in to the h1 tag by including it. 
# Vue Mixin - Data
Mixins were useful for my most recent project I'm working on in Vue. I had a feature where the page would load and until the Axios request was complete. A loader spinner would be indicated on the screen. I had four different components all using the loading feature. In order to implement it, there had to be a local state object of loading. 

```
export default {
    data() {
        return{
            fish: [],
            loading: false,
        }
    },
```

We would then implement logic during the fetch to set the loading to true and switch it back to false at the very end once all the data was received. If loading was true (during us getting that data) we'd show the spinner in the html. I noticed that this loading state was put into 4 different containers! It was also going to potentially be put into more since I'm planning on getting at least 2 more containers into the project. This obviously is not very DRY. This is where Mixins came to the rescue. Their are different ways to create and call mixins but a common and easy one is a global mixins. Global mixins should be used with caution as it will be mixed in to all of your components and should only have functions and data you plan on using throughout your whole project. In this case I believe it suits the loading since It's being used in about every component that is holding state. 

To create a global mixin it is put into your main.js file like so: 

```
Vue.mixin({
  data: function(){
    return{
      loading: false,
    }
  },
  filters:{
      capitalize: function(value){
          return  value.charAt(0).toUpperCase() + value.slice(1)
      },
    }
  })
```

Now we see here that the loading object with a value of false is mixed into all our containers instead of repeating it in every component. Instead of writing it 4 times in 4 different containers, we are writing it once in the mixin. From here it's called and written like any local state object 'this.loading'. 

This is just a brief example of how mixins can be used in Vue. The term is very common in Sass and when it comes to Vue they're fairly similar. I'd suggest always keeping a look out for repetitive code in your Vue applications and using mixins when needed. The global one comes in handy but use with caution. If only needed for one or two components you're better off making a mixin file and then using the needed code to properly import it into a single component when needed. 





