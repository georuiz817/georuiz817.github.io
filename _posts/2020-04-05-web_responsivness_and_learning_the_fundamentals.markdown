---
layout: post
title:      "Web Responsivness and learning the fundamentals"
date:       2020-04-05 16:46:10 +0000
permalink:  web_responsivness_and_learning_the_fundamentals
---


While I have some down time I've decided to work on vanilla HTML and CSS. Sometimes when not working with it and focusing on more full stack projects you can get rusty. The project I'm workign on is inspired by the Netflix tv series Tiger King. It's a landing page for the series where users can watch the trailer, see some images, have quotes from the show generated to them, and get a full list of the episodes. 

I'm working with a UX designer during this time who thought of the idea and is designing the site with Zeplin. From there she exports me the wireframes for the site depending on the break point and I'll write the HTML and CSS. It's funny going from working with things like React and Rails to regular old HTML. You forget how simple it is and how tedious it can be. However, it still is really fun! I remebered learning all of this years ago and being just amazed as I am now. 

Breakpoints were something that was not touched on during my time at Flatiron, so it's something I'm taking this down time to master now. I enjoy making the sites responsive and easy to use for a user, espicially one mobile. Sure it can be a little repetitive if but theirs plenty of ways to work around this and get only what specifically needs to be in that break point. For example in every breakpoint file I had:



	@font-face {
		font-family: SFProDisplay-Thin;
		src: url('../../SF-Fonts/SF-Pro-Display-Thin.otf') format("opentype");
	}

    .Netflix-Logo {
		width: 61px; /* 61px/1280px */
		height: 61px; /* 61px/1280px */
		object-fit: contain;
		margin-left: 1.796875%; /* 23px/1280px */
		margin-top: 1.796875%; /* 23px/1280px */
		display: inline-block;
		margin-right: 11.796875%; /* 151px/1280px */
	}

	a:link, a:visited{
		text-decoration: none;
		color: white;
	}
	
	.nav-info {
		font-family: 'SFProDisplay-Thin';
		font-size: 30px; /* 30px/1280px */
		font-weight: 100;
		font-stretch: normal;
		font-style: normal;
		line-height: 1.47;
		letter-spacing: 0.035156%; /* 0.45px/1280px */
		text-align: left;
		color: #ffffff;
		display: inline-block;
		margin-right: 46px;
	}
	
	
Therefore at this point the home.html file was constructed with: 
home.html
Home(css folder)
* mobile.css (max width 600) 
* computer.css (min-width 1280)
* table.css (min-width 1020)
* tableLandscape.css(min-width 800)

With this every single one of those css files had that navigation css above in it based on it's breakpoint. Which cluttered up the page with nav css code. Making it harder to read all the other css that was necessary to the page. 
Then for another page like the quotes page, that css would need to be in it as well once again cluttering up the pages all for just the nav. 

My solution was very simple to make a nav file with all the breakpoints in it and just import that single nav.css file into each webpage. Now my home page consist

Nav(folder) 
nav.css (consisting of all breakpoints) 

It seems like common sense and logical, but when you forget how much css really gets imported into the header of a vanilla html pge:

		<link rel="stylesheet" type="text/css" href="./resources/css/HomePage/computer.css" media="screen"/>
		<link rel='stylesheet' type='text/css' href='./resources/css/HomePage/mobile.css' media='screen'/>
		<link rel='stylesheet' type='text/css' href='./resources/css/HomePage/tablet.css' media='screen'/>
		<link rel='stylesheet' type='text/css' href='./resources/css/HomePage/tabletLandscape.css' media='screen'/>
		<link rel='stylesheet' type='text/css' href='./resources/css/Nav/nav.css' media='screen'/>



You want to make sure you can make it as DRY and smooth as possible. I'll be starting to implement break points into all my projects to make sure they are mobile responsive. I will also be going back to some old ones as well. I highly suggest 

https://www.w3schools.com/html/html_responsive.asp

for more









