---
layout: post
title:      "Spruse up your code with Icons "
date:       2020-05-31 15:51:08 +0000
permalink:  spruse_up_your_code_with_icons
---


As you create a website theirs a ton of features that you will have available. The common CRUD (create,read,update,destroy) actions will usually be implemented. Not only those actions but a great deal of others like contacts, information, alerts, social media links etc. Theirs a ton of reasons why you could add icons to all of them. Icons could be used for people who have difficulty reading, i.e understanding your websites language if no other options are available, or to add big symbols to make whatever you’re trying to say stand out for things like small screens, and finally just to plain spruce up your code. Icons can make a boring navbar that just says Home and Contact and give it a sleek modern feel with icons of a house and envelope. Below is just a few examples that I’ve encountered before that you can use. 


# Import Icons directly to HTML 
A Super quick way to get icons up and running on a basic html is with Font Awesome. From there you’ll have all the icons they have to offer. I used an example in my Turtles-App logo. A pizza slice icon is displayed next to the title. 

2.	1.	Import Font awesome directly through your head tag

```
<head>
<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.7.0/css/all.css" integrity="sha384-lZN37f5QGtY3VHgisS14W3ExzMWZxybE1SJSEsQp9S+oqd12jhcu+A56Ebc1zFSJ" crossorigin="anonymous">
</head>
```


2.	Use the <i> tag and choose the icon you want displayed

```
<h1 class="text-center htag">Turtles-App <i class="fas fa-pizza-slice"></i></h1>
```

# Bootstrap Icons with Vue
Now as with HTML you could import it directly through a head tag, however it would only be specific for each component. Therefore if you had 10 components youd have 10 imports and not DRY. Therefore you can import all or specific icons through your main.js file. In this example we will be importing all of them. 
Note: Have bootstrap vue ready and installed to your project in which you can than import icons.

1.	In your main.js file import Bootstrap and BootstrapVueIcons

```
	import { BootstrapVue, BootstrapVueIcons } from 'bootstrap-vue'
	
	Vue.use(BootstrapVue)
	Vue.use(BootstrapVueIcons)
```

2. Then from there you can use any icons using the <b-icon> tag from exactly what you need

```
    <b-icon icon="arrow-up"></b-icon>
```

# Icons with React

A way to use it with React is react-icons a quick and easy package that allows you to insert specific icons you need into a given componenet. This would be beneficial if you didn't want to bulk up your project by inserting all the icons a package or provider has to offer. 

1. Add react icons with your package manager 

```
yarn add react-icons
```

2. Import the specific icons into the given component and you can this use it as a syntax

```
import { FaBeer } from 'react-icons/fa';

class BeerExample extends React.Component {
    render() {
        return <h3> I love <FaBeer />? </h3>
    }
}
```

All three examples are unique in there own ways. Whether you're using vanilla html, or a framework like React or Vue, theirs tons of ways to use and import icons. I personally enjoy just importing all the icons so I can use them whenever I want instead of having to go back and import others. However, I'm usually just making a basic website that is not bulky on it's own. If you're worried about bulk or slowing down a site, perhaps you would only import ones you know you're going to need to use. I would always suggest using icons because it elevates a site in a way that job providers or potential employees would like to see. Artistic flare is great and something like a little icon really stands outs! Theirs tons of other ways to download icons and theirs tons of other providers besides font-awesome and bootstrap, I would suggest doing your own research and seeing which ones suit your needs the best. Finally if you want to just toss in a single icons and don't want to worry about imports etc. you can just go to https://emojipedia.org/ and copy and paste an emoji into your HTML! 
	
	
	


