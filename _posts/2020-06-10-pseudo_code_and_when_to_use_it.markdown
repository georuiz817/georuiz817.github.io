---
layout: post
title:      "Pseudo code (and when to use it) "
date:       2020-06-11 00:55:18 +0000
permalink:  pseudo_code_and_when_to_use_it
---


A lot of the time we are coding it can be sporadic. We know what we want to do and we have the idea in our heads. So we go right on ahead and start to code our function/algorithm etc. However, what usually ends up happening is we have bugs and the code is not structured correclty. What this does it make us not only debug and console.log() many of things but we also waste time restructuring and debugging (and scratching our heads). Well a great way to have what you want your function to do and solve is by first writing pseudo code! 

Psuedo code bydefinition is :

'a kind of structured english for describing algorithms. It allows the designer to focus on the logic of the algorithm without being distracted by details of language syntax.  At the same time, the pseudocode needs to be complete.  It describe the entire logic of the algorithm so that implementation becomes a rote mechanical task of translating line by line into source code.' 

src: http://users.csc.calpoly.edu/~jdalbey/SWE/pdl_std.html

So with that being said instead of coding our algorithm we just planly write it out! It gives us time to think about what needs to be done and what needs to happen without all the confusing syntax as we are planning it out. A great example could be while I was writing an algothirim for my search bar on my portoflio. 

# The task
I needed it to be when a user typed in a letter into the search bar, we were forwarded over to another component/webpage. Depending on certain letters we would go to different components or do a certain action. 

# Psuedo code notes: 


Goal: type in a letter into the search bar and go to a specific page 

questions: 

-make it so that it's not case specific (SearchLtr.toUpperCase())
- what letters will do what (use the first letters for each card on the home page)
- will we need any external help? Imports etc. (history.push? to go to another comp) 

Steps towards the algothirm: 

1. make our variable with a value of our state and make it non case sensitive 
2. if we type in the letter a go to about comp
3. if we type in the letter g forward to my github
4. if we type in the letter e go to the edit page
5. if we type in the letter r open up my resume
6. if we type in the letter c go to my contact email
7. if we type in the letter  m go to the menu 

Now with our goal in mine we can use this english language and slowly convert it into syntax. We can see from here that it's going to be a conditional. However, we have it written in plain english now. We can then follow each step and convert each step into JavaScript syntax like so 

1. let searchLogix = SearchLtr.toUpperCase()

2.     if ( searchLogix === 'A'){
      history.push('/about');
			
3.  else if (searchLogix === 'G'){
      window.open(
        'https://github.com/georuiz817',
        '_blank'  
        );
				
4. else if (searchLogix === 'E'){
        history.push('/edit');
				
5.  else if (searchLogix === 'R'){
        window.open(Resume, 
        '_blank'
        );
				
6. else if (searchLogix === 'C'){
        window.open("mailto:ruiz.fullstack@gmail.com"
        );
      }
			
			
7. else if (searchLogix ==='M'){
        history.push('/menu');
      }
			
we have mapped each and every step into a JavaScript syntax just by converting the basic high level english into JavaScript. It lets you seperate each piece and udnerstand it fully before coding. Now with it all together we have 


```
  const handleSubmit = (e) => {
    e.preventDefault();
    console.log({SearchLtr})
    let searchLogix = SearchLtr.toUpperCase()
    if ( searchLogix === 'A'){
      history.push('/about');
    } else if (searchLogix === 'G'){
      window.open(
        'https://github.com/georuiz817',
        '_blank'  
        );
      }else if (searchLogix === 'E'){
        history.push('/edit');
      } else if (searchLogix === 'R'){
        window.open(Resume, 
        '_blank'
        );
      }else if (searchLogix === 'C'){
        window.open("mailto:ruiz.fullstack@gmail.com"
        );
      }else if (searchLogix ==='M'){
        history.push('/menu');
      }
    } 
```

and we are done! This was a very simple problem however you can see the gist of what needs to be done. You need to find your goal, plan out what questions or road blocks might come out of it. Then write each step you believe will need to be done in human language. From there you can convert it to syntax later step by step. This will let you right cleaner, more precise, and quicker code overall. You're not fumbling around trying to have the idea in your head all the while writing it in non human language. 

# Other tips for pseudo code
It's great to use this by yourself. However, if you find yourself in a team situation and are struggling to solve a problem use it too! You can use this as a kind of brain storming session with your co workers or team mates. It puts all the code and different coding styles aside and breaks it down to just a conversation. Have some one lead the conversation and jot things down while everyone else openly talks. 

Also don't over use it! Some things like HTML don't need to be over simplified. If you have a clear cut picture in your head on what needs to be done and you're confident you can tackle it go for it. 


