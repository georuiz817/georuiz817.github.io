---
layout: post
title:      "Debugging Time! HTTP VS HTTPS"
date:       2020-05-04 00:46:34 +0000
permalink:  debugging_time_http_vs_https
---


Being deep into my Horizons Library front end project, I've already had it deployed to Heroku!

horizons-library.herokuapp.com/

But wait... Why is it 'horizons-library.herokuapp.com/' with no HTTPS? Their is a very simple reason why I had to do this during the project. It was quite a journey figuring out how to.

I was noticing testing my site on localhost it was working fine. I was able to GET my objects from ACNH API, a third party API that deals with everything Animal Crossing in JSON format. But when moving on over to heroku, I noticed when I'd go to my index component for the GET requests, nothing was coming up. Just an infinite loading spinner. I was extremely confused and not entirely sure why this was happening. So I started to get to debugging.

I was seeing in my console the error 'Blocked loading mixed active content "http://acnhapi.com/fish/"'. I truthfully had no idea what it was. All my projects for the most part have been local projects. Apart from WordPress and my portfolio which does not make any requests I'd never had my work with live sites. So I just copied the error and Google'd it. A ton of articles from GitHub and Stack Over Flow popped up. It seemed like a lot of people especially using Heroku where also in the same pickle as me. But weirdly enough, I couldn't find a way to fix it. A lot of people were suggesting on my Axios request to change - 


```
  axios.get('http://acnhapi.com/villagers/')
```

to 

```
  axios.get('*https*://acnhapi.com/villagers/')
```

So I did and well that didn't work.. I was getting even more errors and thought their was probably a better solution. So I thought maybe I needed to go to the source and see if they knew anything. The creator of ACNH API had their discord contact info on the API site so I went ahead and shot them a message. Basically just introduced myself and sent over the bug, and asked if anyone using their API ever had any problems in regards to the same issue. He then explained what was wrong on his end and it hit me exactly what was the problem. 

His site wasn't deployed with a HTTPS certificate. The site even was a HTTP and not HTTPS site as well as his directions for his GET requests to be in HTTP. Meaning his site was running on an unsecured network. He was using a basic express sever and had yet to get it secured. Therefore, when attempting to post the data to my Heroku site which is secured by default, un-secure data from the api was being blocked. HTTPS security will not allow un-secure data to be sent in resulting in the mixin error. So after some more research on exactly how to fix the situation it was really simple. Run the site with HTTP. Therefore they both will not be HTTPS and will not result in a error, data will be able to flow through both of them. You'll see whenever I post my site on LinkedIn, my portfolio etc it's in HTTP format to allow the user to get the data from ACNH API, if you try to run it any other way you'll get the error.

In the end it was a pretty silly error. If I had some additional knowledge before hand on the matter it was an easy fix. Not even a fix because none of the code had to change. More or less just how I present it on my resume, links, etc. I would highly suggest if anyone ever runs into a issue, reach out to someone! Or do some heavy research on the subject. Once you find out how to fix it, keep researching the subject! Learn as much as you can about it so you have the proper knowledge if you ever encounter another bug on the topic. 
