---
layout: default
title:  "Random Quote Machine - Guide"
meta: "Don't know where to start? Use this rough guide to building a Random Quote Machine"
date:   2017-06-15 15:43:14 +0200
category: jQuery

---

<h1>Random Quote Machine - Guide</h1>

If you are anything like me, you may have gone through the freecodecamp tutorials and explanations feeling confident until you get to the projects... Where to begin? APIs, Jquery, getJSON? How do you link all of that together to create a functional web application? Well, my goal is to bridge that gap from completing interactive tutorials to creating projects.

Now, this isn’t an in depth tutorial but a guideline which I will outline the the steps and considerations that you may take in creating a Random Quote Machine using the knowledge you have gained from freecodecamp. My aim is to nudge you in the right direction and so you can practice the things that you have learnt in FFC without showing you exactly how to do it.

If you get stuck at any point try to identify what exactly you are stuck on, google it, if that doesn't help take a look at [my code](https://codepen.io/mierz/pen/XMPXMa?editors=0011). Failing that, head over to the freecodecamp chat rooms or send me a message. I have also provided links to relevant information and further reading.

## Why use API's?
TODO

## Step 0 - Analyse
First things first, take a look at [here](https://www.freecodecamp.com/challenges/build-a-random-quote-machine) and [here](https://codepen.io/mierz/pen/XMPXMa) and identify what you will need in the project.

- Tweet Button 
- Next Quote Button 
- Area to display quote 
- A JSON request to a quotes API. 
- Twitter intent url. 

Have a little think about how you want your design to look and how to set it up, note the url link when clicking the Tweet button, that will come in handy later

## Step 1 - Setting up codepen.io
- I like to do a simple hello world page before I do anything. 
- Go into settings and add all the dependencies you want. For this project we will only require JQuery. 

## Step 2 - The design
A lot of people have different ideas on this, but I prefer to create the design of my application first. 

1. Create a rectangle shaped div which you can style as you like, I rounded the borders and added a grey background. 
2. Create another div inside where the quote will go. Give this div an id of ‘quote’ to use later on with Jquery. 
3. Create two buttons, one for tweeting the quote and another for generating another quote. Give both of those buttons an id. 

I positioned everything on my screen using flexbox, if you are unfamiliar with flexbox I strongly suggest taking some time to learn what it's about. It will make life much easier to position CSS elements.[What the flexbox?!](https://flexbox.io/), [ A guide to Flexbox](https://css-tricks.com/snippets/css/a-guide-to-flexbox/)

My design so far looks like this 
![]({{ site.url }}/assets/random-quote-machine/ss1.png){:class="img-responsive"}


## Step 2 - Connect to the API
This tends to be the most confusing part, the aim is to connect to an API and fetch data which you will be able to use in your webpage. For this project we want to connect to a quote API. Here is a[link](https://api.forismatic.com/api/1.0/?method=getQuote&lang=en&format=jsonp&jsonp=?) to one of them, however you can use which ever API you like. 

Note: if you use Google Chrome you can install [JsonView Extension](https://chrome.google.com/webstore/detail/jsonview/chklaanhfefbnpoihckbnefhakgolnmc?hl=en) so that when you open a JSON file in the browser you can view the way the data is formatted. This will be helpful when you have to access that data later.[Forgotten how to access objects?](https://www.freecodecamp.com/challenges/accessing-objects-properties-with-the-dot-operator) 
![]({{ site.url }}/assets/random-quote-machine/ss2.png){:class="img-responsive"} 

1. Create some global variables to store your author and quote. 
2. Set up a getJSON function using the API [link](https://api.forismatic.com/api/1.0/?method=getQuote&lang=en&format=jsonp&jsonp=?) and console.log the response from the API. Here is an example of a getJSON request 
```js
 $.getJSON( "test.js", function (json) { 
        console.log(json.users); 
     });
```
   
4. If you have issues with getJSON, revisit the [getJSON](https://www.freecodecamp.com/challenges/get-json-with-the-jquery-getjson-method) tutorial again to see if you can work it out. 
5. You should be able to see something like this in the console 
![]({{ site.url }}/assets/random-quote-machine/ss3.png){:class="img-responsive"}

## Step 3 - Connect the Data to HTML
1. Notice, that we have a plain javascript object from our getJSON request. Now we can access that object just like you would any other javascript object. 
2. Set up a new function and place the getJSON request inside. We will use this function when the page loads and when the 'next' button is pressed. 
3. Assign the data from the getJSON request into the two variables author and quote for example: 
4. Use .html to modify your text area to display your quote and author, if you're unsure how to do this, revisit the [Convert JSON Data to HTML](https://www.freecodecamp.com/challenges/convert-json-data-to-html) tutorial. 
5. Call your function 
6. You should have something like this when the page loads 
![]({{ site.url }}/assets/random-quote-machine/ss4.png){:class="img-responsive"}

## Step 4 - Tie up 'Next' Button
1. Utilise the jQuery ```.click()``` function to add your getQuote function inside. 
2. Now you should be able to click on the 'next' button and a new quote will appear in your div. 

## Step 5 - Tweet Button
1. Once again use the jQuery ```.click()``` function to add functionality to the tweet button 
2. In order to open a new window of a link, you can use 
3. window.open(URL) 
4. [Click here](https://dev.twitter.com/web/tweet-button/web-intent) to get information and an example of using the Twitter web-intent url 
5. Utilise your author and quote variables to create a url for the 'tweet' button. 

## Step 6 - Finishing up
You should now have a functional Random Quote Generator, feel free to improve the design and make variations to your code.

Remember if you are having issues, go through the steps and identify exactly what you are unsure of. Go back through and redo Free Code Camp tutorials and google the issue.

![]({{ site.url }}/assets/random-quote-machine/ss5.png){:class="img-responsive"}

 