---
layout: post
title:      "All about... About pages "
date:       2020-05-10 20:45:45 +0000
permalink:  all_about_about_pages
---

While coming to the end of my Vue.js project Horizons Library, only a few more things are needed. I plan on getting in a footer component with my socials and an about page. I have struggled with about pages in the past. Theirs so many different options on layout, imaging, and information. They are extremely important though to get your message out. If you site is meant to be live/retail that's great. You'd probably have some facts about the history of the company and your what the company itself is about (duh). 

However, you might want to explain things in more context if you're trying to showcase your skills. Doing projects at this point in time is not for me to make money and build a company as a entrepreneur. I'm trying to land a job! Therefore, for any one who's in the same space as me, you might want to talk about your code that built the project, why you used a certain tool during the project, and future steps. It's more of a technical about page. It will showcase more of what the person is about that is coding it, not the actual site. 

Using Vue.js I've decided to use a few tools for the about page and the rest of my site. For starters, Bootstrap Vue is going to come in real handy. Using the grid system, I'll be able to show wireframes, the code that is running the site, and the architecture of files that is holding the site together. 

The grid system will let me layout the overall page beautifully. If you know Bootstrap that's great! Using Bootstrap vue is not too far off only now we will be using the <b-> in front of each tag for example in my layout of the about page: 
(more information on how to use Bootstrap Vue https://bootstrap-vue.org/docs/components)



```
<b-container>
  <b-row>
    <b-col>Paragraph</b-col>
    <b-col>Code example</b-col>
    <b-col>screen shot of the live site that code was used in</b-col>
  </b-row>
</b-container>
```


Then from there, depending on how big I want the code block to be, or the paragraph I can add things like:

```
<b-col col lg="2">
```

Using the 12 sized grid system, that col will now take up only 2 of 12 blocks, making it pretty tiny. That would be ideal for maybe a quick note or blurb about an image or code. 

There is a ton of different about page examples you can look out to really get a feel of what you want. One great example is here https://blog.hubspot.com/marketing/remarkable-about-us-page-examples. However, I believe I will being going with my about code which is a much more simplistic approach. Just to really get the message out there. It's great to how that cols and rows to line everything up perfectly. Especially because Bootstrap Vue is going to make your site mobile responsive as well. I highly suggest reading the Bootstrap Vue official site for details on how exactly to structure you code and how the tags now differ from traditional Bootstrap. 

Displaying the architecture of the site will be fantastic on the about page with the chosen layout. In coding, things can get messy very quickly. Tons and tons of folders, sub folders and files. Each having different uses perhaps in the design or in the components of in the back end etc. That's why it is important that you can show you are organized and I have knowledge on a steady, clean workflow to employers. 

```
Src 
   v assets
	   > images
   v components
     v FishComps
		       -FishIndex.vue
				   -FishShow.vue
     v VillagersComp
           -VillagerIndex.vue
			     -VillagerShow.vue
    About.vue 
		Footer.vue
		Nav.vue
    App.vue
    main.js
```

This is just a rough typing of my layout at this moment. It's perfect for what it needs to do currently. Instead of having everything dumped right into the components folder, or not even having a components folder at all, it's structure by a theme. For example all the Fish pages that are going to have GET requests are in the FishComp folder, and their respected show and index are in separate files. Same for the Villagers and soon we will get the navigation and footer in their own folder (top and bottom of page) as well as anything other theme that might come into play. This is a good basic start to just dumping everything into your project. 

Going from here, I'm going to make sure to code out my about page as best as possible. I assume my next blog post will show a snippet of it and any other pointer I may add to making one. For any one making an about page for a product or even their personal portoflio, good luck! 

