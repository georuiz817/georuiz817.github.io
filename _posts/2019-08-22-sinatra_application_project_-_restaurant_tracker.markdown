---
layout: post
title:      "Sinatra Application Project - Restaurant Tracker""
date:       2019-08-22 18:53:45 -0400
permalink:  sinatra_application_project_-_restaurant_tracker
---


My second project in my Flat Iron software-development was to build a  MVC model Sinatra application. The project had to have a few key requirements ranging from a correct use of models, SQL, and routes. I decided to make Restaurant Tracker which a logged in user could note their favorite restraurants and edit them as well. 

Creating the environment (how the application runs) : I used a few different files to get the environment of my project up and running (ex: config.ru, environment.rb, rakefile, gemfile.) Below I have listed a few of my favorites to work with. 

- use of gemfile  

`source 'https://rubygems.org'
### gem 'rails'
gem 'sinatra'
gem 'activerecord', '~> 4.2', '>= 4.2.6', :require => 'active_record'
gem 'sinatra-activerecord', :require => 'sinatra/activerecord'
gem 'rake'
gem 'require_all'
gem 'sqlite3', '~> 1.3.6'
gem 'thin'
gem 'shotgun'
gem 'pry'
gem 'bcrypt'
gem 'tux'
gem 'rack-flash3'`

Although I personally did not use all of the gems, I suggest to have at least the basics avaliable. I don't tests like binding.pry and capybara. However, they are good to at least have in your gemfile if you want to use them at anypoint in time. If you're going to have a login ft. bcrypt is HUGE. It'll make sure you have that appropriate methods to have a good seucity system :). 


- use of rakefile / migrations 

I used rake db:create_migration NAME="create_restaurants" and rake db:create_migration NAME="create_users for my SQL tables. From there I would be able to map out exactly what each instance restaurant would contain and what each user would contain. 

```
class CreateRestaurants < ActiveRecord::Migration
  def change
    create_table :restaurants do |t|
      t.string :name 
      t.string :location
      t.string :wifi_avaliable 
      t.integer :user_id
    end
  end
end

    
class CreateUsers < ActiveRecord::Migration
  def change
    create_table :users do |t|
      t.string :email
      t.string :password
      t.string :password_digest
    end
  end
end

```


Routes/Controllers (routes of the application): 

For my MVC outline I used two controllers application_controller and restaurants contoller. The application controller would control the routes for my Login and Signup while my restauraunt contoller would controller the routes of editing, creating, viewing, and deleting a restaurant. What did all of these routes render? My views! 

For resturaunts - 

edit.erb	(html page for editing a restaurant)
index.erb	(shows all a users restaurants) 
new.erb (html for creating a new restaurant) 
show.erb (shows a page of the specific restraurant just created) 
login.erb (html page for logging in) 
signup.erb (html page for signing up) 

Personally for me, this was my favorite part of the project. Coming from someone who mainly enjoys doing front-end development over back-end having the ability to play around with HTML was great. Laying our each page properly will make your application easy to use and give you as the coder a better understanding of what each page does / how to route it. For each views page I didn't enjoy that everytime you clicked a blue link it would turn purple for the remainder of the application use. This especially got annoying when I was going through the project over and over making sure it worked properly. To rectify this I through in a little inline - css for the few pages. This seemed easier to do real quick for all 4 view pages instead of making a css function espicially since it was only one line of code. Unfortunatley due to time and the sake of my presentation to show I can use Sinatra, I didn't use any other css or fancy html tricks. 

```
<style>
  a:visited {color: blue;}
</style>
```


Strugglers in my project: 

My hardest struggle in this project was well.. What to make it on. Looking back on my OO project, I reazlied I enjoyed doing the hard work b/c if was something I was interested in - Pokemon! Therefore, I had to make sure this time around on a much more complex project that it also was something I liked. Being a lover of all kinds of coffee I decided to do it on cafes! However, after a completing all the good I was getting a "Could not find table "caves"" error. What could this of been? Well apprently the word cafes is something the migration isn't so good at using and it was attempting to convert it into the word caves causing a crash in my project. With this being said I had to change all my code (models, instances, routes) and drop my migrations and re-name them all. Luckily i'm also a lover of food and decided to make it on resturaunts. 


Take away: 

Overall I enjoyed my Sinatra project. I really enjoyed the front-end aspect and the rake/SQL aspect. So far throughout the course  SQL was something i've been enjoying. The ability the organize and create tables for data management seems very pracitcly and something to use in a real-world scenarion outside of coding. 







