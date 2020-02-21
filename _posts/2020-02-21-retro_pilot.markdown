---
layout: post
title:      "Retro Pilot"
date:       2020-02-21 20:52:55 +0000
permalink:  retro_pilot
---

To take a break from my portoflio I've decided to make a new project. Retro Pilot is a clone of a palm pilot with all the usual features. Address book, memo, to do list, weather, calculator etc. It's going to implment React Hooks instead of traditional components. The reason why I've decided to go with hooks and not React/Redux is to get practice with hooks. 

The full stack project is going to be a React/SCSS front end with a Rails API/SQlite back end. There will be roughly 5 different objects all with there own unique and individual properties. With that many objects I'll be doing alot of fetch requests to the api what is exactly what I'm looking for. Fetch requests are something I'd like to have more confidence and be stronger in.  I would like each individual CRUD action to have it's own request with local state instead of using a store, action, and reducer. It would be less "DRY" in that sense that each component page made be a little cluttered with fetch requests but that is okay. This is not a "production" project it's for practice and to have another project under my belt. 

So far on the project hooks have been great. I actually enjoy them more than a typical constructor and state. It makes it quicker and cleaner to have all the components as functional components as well. As of now the Addresses section is done and I will start working on maybe the weather component. Weather will be interesitng because it will not be taken from my API but from a live API weather source. 
