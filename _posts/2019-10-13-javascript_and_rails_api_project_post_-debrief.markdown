---
layout: post
title:      "JavaScript and Rails API project post -debrief "
date:       2019-10-14 03:38:28 +0000
permalink:  javascript_and_rails_api_project_post_-debrief
---


Yup I've completed my project... It meets the requirements and does what it needs to do in some ways elegantly and in some ways like if you tried to fix a rocket ship with duct-tape. The rocket ship will still work... It was just fixed very odd way. 

I've decided to make a Ninja Turtle Pizza feeder. Ninja Turtles love pizza! The requirement break down for my project is as follow 


Rails API: 

- Models

Model 1: turtle Has many pizzas
Model 2: pizza Belongs to turtle

- Routes

GET
/pizzas
pizzas#index

POST
/pizzas
pizzas#create



JS Front End: 

- Models 

Model 1: turtle 
Model 2: pizza


fetch: 

Model 1: turtle we have the ability to get all turtles (the two I seeded into my db, you will not be able to create a turtle) and display them on the front end

Model 2: we have the ability to submit pizzas created in our js front end to the back end to be saved to the database pizzasubmit, and we have the ability to get all the pizzas from the back end database and render them in a list on our front end. 

Events 

1. Dom Content Loaded which will  get all our pizzas,turtles and give us the ability to have a submit pizza event 
2. addSubmitEventToPizza which will once upon submission (clicking our submit button) will  send our newly created front end pizza to the back end to be saved to the database. 


One thing I struggled with and will contiune to attempt to fix: 

Is when I am rendering my  li for all the pizza objects I also want to show the pizza.turtle.name that it belongs to on the back end. However, in my pizza class / constructor i'm getting a error while attempting to do this. My work around was that I show with my getTurtles method the 2 turtles and list there id's for the viewer, then while the pizza objects are listed out you'll get the turtle_id ex:


```
 <h1> Ninja Turtle Pizza Feeder </h1> 
    <h2> Here are the turtles we will be working with today</h2>
    <ul class="allNames"> 
        </ul>
```

Above shows all the turtle objects that were taken from the Api database. 


Then 

```
 <h4> Here is all the Pizza the Ninja Turtles has been fed so far:</h4> 
         <ul class="pizza-list"> 
             
         </ul>
				 
			```
			
		above shows all the pizza objects taken from the database however when the pizza attr are listed in the above is shows the turtle_id not turtle name. Therefore, i used needs to remeber which id belongs to which turtle. Which is fine when theirs only two and for the sake of the project it works. But I would deff like to fix that up. 
		
	
	
Overall the project I believe went well. Doing my own research, discussing ideas with classmates, using outside websites, and re-watching my cohorts recorded live lectures  were all great tools I used to complete my project. I would say I have a better understanding now of JS and that with even more practice I could master it's art. 

Feed back for FlatIron : Being one of the first cohorts to take this JavaScript cirriculum I will say that it is a work in progress and has some growing pains. I wish throughout we would've focused more on things we would've actually used in our project. Instead of a majority of the getter, setters, super, Prototypal inheritance, advanced functions information. Now with that being said,*** I know that all of the above is very important and is JS fundamentals*.**  But When I was trying to create a piece of pizza and feed it to a turtle I didn't really use setter and getters, or even super. 

On my project things that seemed more important to have info on where -

Fetch involving submitting data and getting back data and how to use it on a project, setting up a rails api back end properly , event listeners, and how to manage your files in your javascript front end like creating  a API file that would have all your fetches and creating a global.js folder to hold all your global variables. These all to at least me while setting up my project were things I wish the cirriculum dove deeper on. However, overall i'm very excited to move forward and move on to React! 










