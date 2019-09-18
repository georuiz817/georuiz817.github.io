---
layout: post
title:      "Poke_TM Rails"
date:       2019-09-18 16:27:25 +0000
permalink:  poke_tm_rails
---


Hello! This is my third Blog during the FlatIron School course. Today my blog will be touching my work through the Rails Portoflio Project. 

Before reading any further! If you don't have knowledge on Pokemon I suggest reading 
https://en.wikipedia.org/wiki/Pok%C3%A9mon 


1. Requirement: Include at least one has_many, at least one belongs_to, and at least two has_many :through relationships


• With this being said I decided to make my models and associations through users, pokemons (to not get confused with singular and plural) and Tms. A user should be able to equip a Tm (a "technical machine" aka a pokemn move that you can attach to a pokemon like a piece of jewlery)  to one of there Pokemon. A user would then have many Tms through the Pokemon that them equipped and a Tm would have many Users through the Users pokemons that have them. 

So with these associations being said my models look like so => 

User: 
      
			has_many :pokemons
      has_many :tms, through: :pokemons 
			
Pokemon: 
      
			belongs_to :user
      belongs_to :tm
			
Tm: 

    has_many :pokemons 
    has_many :users, through: :pokemons 
			
			
2. Requirement:  Your models must include reasonable validations for the simple attributes. You don't need to add every possible validation or duplicates, such as presence and a minimum length, but the models should defend against invalid data.


•  I used basic validations for this part. Just requiring prescence and minimum lenght for a Users password. I planned on trying to figure out a way to make it so a User can have only five pokemon in there group like the game. However, I think i'll try to tackle that at a later time post course. 

User:

    validates :trainer, presence: true
    validates :email, presence: true, uniqueness: true
    validates :password, length: { minimum: 5 }


3. Requirement:  You must include and make use of a nested resource with the appropriate RESTful URLs.
You must include a nested new route with form that relates to the parent resource
You must include a nested index or show route


•  For this topic a User can create pokemon for them and edit,delete,view,view all. Within in my routes file I have the nested route. 

 resources :users do
 resources :pokemons


users/:user_id/pokemons => view all a users pokemon 

users/:user_id/pokemons/:pokemons_id => show a specific users pokemon 

users/:user_id/pokemons => view all of a users pokemon 

4. Requirement: Your application must be, within reason, a DRY (Do-Not-Repeat-Yourself) rails app.

• Finally I have forms  to have a Dry Views. Specifically the home button. My project does not have a nav bar so a user is going to need to be able to navigate back to the home page at any point in given time. I did this by creating a form with <%= linkto "Return Home", rootpath %> with rootpath being the home page. For every pokemon or user view page i have the  <%= render 'welcome/form' %> at the bottom.  


Conclusion: 

Overall I did enjoy this project. It did give us a strong understanding of basic rails and how to create a project from scratch. This will also help give us a strong MVC understanding when out in the real world. I am now excited to move on to Javascript and see what that entails. 

	
	
	
	
	

