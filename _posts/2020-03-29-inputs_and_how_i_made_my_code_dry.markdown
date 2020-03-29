---
layout: post
title:      "Inputs and how I made my code DRY"
date:       2020-03-29 16:23:11 -0400
permalink:  inputs_and_how_i_made_my_code_dry
---

Working and always adding to my Web Developer portoflio, I thought of a new idea for it. I was going to make a edit page so a user can change the background, text color, and font, and cursor of the portfolio to whatever they wanted to with a simple click. The idea was to have buttons with options that a user can click and it would change. Simply enough in my React project in the container component for the edit page I through in this: 


```

 import React from 'react'
import {Col, Row } from 'react-bootstrap';

const PinkBack = () => {document.getElementsByTagName('body')[0].style.backgroundColor = 'pink'}
const GreenBack = () => {document.getElementsByTagName('body')[0].style.backgroundColor = '#52ff51'}
const OrangeBack = () => {document.getElementsByTagName('body')[0].style.backgroundColor = 'orange'}
const YellowBack = () => {document.getElementsByTagName('body')[0].style.backgroundColor = 'yellow'}
const BlueBack = () => {document.getElementsByTagName('body')[0].style.backgroundColor = 'blue'}

const PinkFont = () => {document.getElementsByTagName('body')[0].style.color = 'pink'}
const GreenFont = () => {document.getElementsByTagName('body')[0].style.color = 'green'}
const OrangeFont = () => {document.getElementsByTagName('body')[0].style.color = 'orange'}
const YellowFont= () => {document.getElementsByTagName('body')[0].style.color = 'yellow'}
const BlueFont = () => {document.getElementsByTagName('body')[0].style.color = 'blue'}

const Arial = () =>{document.getElementsByTagName('body')[0].style.fontFamily = 'Arial'}
const Script = () =>{document.getElementsByTagName('body')[0].style.fontFamily = 'Brush Script MT, Brush Script Std, cursive'}
const Console = () =>{document.getElementsByTagName('body')[0].style.fontFamily = '"Lucida Console", Monaco, monospace'}
const Impact = () =>{document.getElementsByTagName('body')[0].style.fontFamily = 'Impact, Charcoal, sans-serif'}
const Cursive = () =>{document.getElementsByTagName('body')[0].style.fontFamily = 'Apple Chancery, cursive'}


const EditComp = () => {
  return ( A BUNCH OF CODE 
	```

Now I'm sure you can see the problem there. For one it's in no way DRY (don't repeat yourself). We are using practically the same blocks of code besides changing the style at the very end. It's cluttered and messy. When some one would go to look into the component they'd be pretty confused on how to navigate this. 

I wanted to go one step further and get all that pesky unDRY code out of the component. So how did I do that? Well I made a make shift helper.js component and imported it into this one having each block look like this: 

```
 PinkBack: function(){
        document.getElementsByTagName('body')[0].style.backgroundColor = 'pink'
    },
```

Then would call each function with

```
onClick={EditHelpers.PinkBack}
```


Basically everything was the same, still the same amount of code that is unDRY but, at least it's stored away in another component where no body can see it. Finally I was doing some research on colors with JavaScript how to manipulate them and how to make everything less DRY. I found my soulution and it seemed pretty obvious once I read it. Our input tags have a type that results in color! All I had to do was set a input type to color and I had every color at the users disposale, not just the 5 I made into squares with CSS with the click function. Now users realy could have more options. With that all I had to do was make the onClick function as simple as 

```
 ColorChange: function(){
    document.getElementsByTagName("body")[0].style.backgroundColor = document.getElementsByClassName("ColorPickerName")[0].value;
    },
```

Now when a user chose the value(selected color) for the input (with a type of color) and clicked the button(with an onClick function of the above code block) it would change to that! Way less unDry and gave the user more options. 

It seems silly now looking back that I had to go through those two silly ideas only to get to the correct one, but that's my journey through coding has been so far.  A lot of mistakes, weird ideas, and eventually finding out the best solution. I'd encourage everyone to keep playing with one of their features on their site and really seeing how they can make it as DRY as possible and as best for the customer that they can. Also, always do your research! If I would have researched colors from the start and brushed up on it, I would have found the solution way quicker. 


