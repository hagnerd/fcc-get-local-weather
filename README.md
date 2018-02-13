# Local Weather App

This application is from the Free Code Camp *Intermediate Front End
Development Projects Section*.

## Goals

* Demonstrate ability to use APIs like the built in HTML 5 Geolocation API and the Open Weather Map weather API
* Demonstrate ability to manipulate the DOM
* Demonstrate ability to design user-friendly front end

## User Stories

* I can see the weather in my current location
* I can see a different icon or background based on the current weather
* I can push a button to toggle between Fahrenheit and Celsius

## My experience

This section *Intermediate Front End Development Projects* is much more independent, and a little harder to wrap your head around. However, I think this independence is important because it means understanding what problems you are having, and demonstrating your ability to look for answers and solutions on your own. 

There are many ways you can handle the assignment. I wanted to go for a jQuery-less solution because I think it's important to understand how to do things in plain-old-JavaScript. jQuery can help a lot with API calls, but it abstracts a lot of the understanding around what is actually happening. 

---

I noticed that the Geolocation call takes a while to return the information, and to a user who comes to the page, they might think it's just a mostly blank page, so I thought it was important to provide some sort of animation to indicate that the page was working and loading. 

The animation was written entirely in CSS and manipulated with JavaScript to be shown and hidden when the call went out, and data was returned.

I also thought it was somewhat jarring for the user to just have the information pop in so I wrote a fade-in animation that scaled into place and went from being transparent to opaque. 

Figuring out how to toggle the temperature between Fahrenheit and Celsius  was interesting because I tried to stick to a some-what object oriented style for this project. Because I didn't want to make another API call to Open Weather Map with the unit specified as either imperial or metric, I decided to default to imperial (sorry non-US people), and then calculate the temperature in Celsius, which is much less time consuming and can be done on one simple line.

When the user clicks the link it triggers a toggle function attached to the weather object, which flips imperial to false, and calls an update.temp function on the view object. 

This allows the animation fade-in animation to be re-run which indicates to the user that an element on the page is changing, and the user can freely toggle between the two states without having really wait for anything to be loaded because the weather object already has the temperature in Fahrenheit and Celsius stored.
