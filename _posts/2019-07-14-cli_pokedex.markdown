---
layout: post
title:      "CLI Pokedex:"
date:       2019-07-14 18:06:20 -0400
permalink:  cli_pokedex
---


Hello! This is first blog and I have decided to do it on my CLI Project. 

1.Thinking of a project idea: I originally started with the idea of a doing it on books. I would then be able to enter into a book using a number system and would retreive the title,author,price etc. However, after some time working on the book project I grew bored. I decided to take the time instead and do it on something I found interest in. Due to the fact that the project may be time consuming. I wanted to make sure whatever I did it on really intruged me. 

Deciding on an idea: Ultimatley I decided to do my project based on Pokemon. For anyone who may not know what Pokemon or a Pokedex is feel free to view https://en.wikipedia.org/wiki/Pokémon. 

2.Getting into code: 

I started my project with the bin. I personally enjoy making Case statements and making levels of text. The case statements allowed me to "map" out what exact infromation the user would be retreiving.  

 - here is a short sample of my case input
    
	
  `when "1" 
	puts "Name: #{dex_1.name}"
	puts "#{dex_1.gen}"
	puts "Type: #{dex_1.type}"
	puts ""
	level_2

	when "2" 
	puts "Name: #{dex_2.name}"
	puts "#{dex_2.gen}"
	puts "Type: #{dex_2.type}"
	puts ""
	level_2`

		
- after some time I decided to change it up to heredocs. The code not onlny looks far cleaner, but easier to understands and makes the project more DRY. 


  
 `input = gets.strip 
   case input
    when "1"
    puts <<~DOC
    Name: #{dex_1.name}
    Generation: #{dex_1.gen}
    Type: #{dex_1.type}
    Height: #{dex_1.height}
    Weight: #{dex_1.weight}
    Physiology: #{dex_1.phy}
    DOC
    level_2 `


		
Obects and Oreintation: I used a few objects to showcase the attributes of the Pokemon.  Name, Generation, Type, Height, Weight, Physiology. Each one would then be scraped via  https://pokemon.fandom.com/wiki/ and the information would be passed into the case statements. 

`attr_accessor :name, :gen, :type, :height, :weight, :phy`

Scraping:  Using  https://pokemon.fandom.com/wiki/ I was able to scrape the data I needed. As you can see it was then transfered into my lengthy heredoc. Looking back on the project I think I would've taken the time to figure out a way to condense the hard code in the heredocs. 

Struggles: What I probably struggled most on was actually the initial set up of the gem. I needed to make sure all the "requires" were in the correct folders and everything would work correctly. I mainly did this via trial and error running the bin and seeing if it would work. I'd like to improve my ability on requires by learning more and figuring out from the start where and when things should be. 

Conclusion: I believe this was a great project to sink our teeth into as new students. It wasn't too difficult but gave us a challenge. I personally would love to create another project like this on something I love again just like pokemon. 
		
