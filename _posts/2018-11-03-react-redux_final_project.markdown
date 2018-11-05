---
layout: post
title:      "React-Redux Final Project"
date:       2018-11-03 13:04:06 -0400
permalink:  react-redux_final_project
---



Almost to the finish line! I’ve completed my React-Redux portfolio project - just need to get through my assessment and then it is graduation time!

After the JavaScript async section I found the React-Redux curriculum much easier to process. I struggled a bit with some of the syntax (when to use those curly brackets still gets me) but the fundamental concept of building a SPA with React seemed pretty natural. Routing was a little odd, but the basic way you break down an application into containers and components made a lot of sense to me.  Plus, I found the React documentation WAY more readable than the MDN documentation. I appreciate the way they walked you through the process.  And, there are SO MANY great resources out there on React.  There are tons of great blogs posts, Medium has some great stuff and the community support out there on the web is just amazing! 

Ok, enough gushing about React.  Let’s talk about things I struggled with during the process of building my Final Project. First, I decided I wanted to use a free weather API. I wasn’t entirely sure how I would incorporate it into a project that would meet the requirements, but I wanted to challenge myself to use an API that we had not used during the curriculum and this one seemed pretty straight forward. Shocker…I fought with it quite a bit.  APIs always seem to require a bit of wrestling. In addition, it was recommended that my Rails API fetch the weather API data for my React front-end.  I was a bit confounded by this suggestion since I could not recall ever fetching data with Rails but after digging around the web I came across Faraday and that sounded familiar. It was part of the JavaScript/Rails async section which I had floundered through so it was no wonder I had forgotten about it.  It worked great! After sorting out getting the weather API data to my React front end I realized that a.)I didn’t need it all b.) I was not excited about how the data was formatted and c) the API has limitations on how many hits per minute you can make before they turn off your key…and the documentation on that limit was a little unclear (is it no more than once per 10 minutes or no more than 60 hits per minute..meh?).  Given these conditions I decided to store the weather data in my Rails API, so I could control the format that was fed to my React front –end), and so I could attempt to control the number of hits to the  Weather API(I only fetch data for a particular zip code if it is more than 30 minutes old).   This didn’t help if someone decided to hit 15 different zip codes one after the other, but it was something.  Given that I needed to check the updated_at time of my weather object in Rails against “now” I had the opportunity to revisit  Ruby’s  Time object and attempt to wrap my brain around how that works and how Rails stores time in the DB.  Always a fun time!

Next up I needed to figure out what to do with my weather data.  After a lot of fiddling with various ideas I decided to build an app that would make a suggestion for an activity based on the currently provided weather.  I built out an activity model and a condition model (based on conditions provided by the weather API) and a join table for the two in my Rails back end and created some seed data. 

Once I had the backend set up I needed to start working on accessing that data in my React app. I had already set up the store for the weather data . I built on top of that for my activities and conditions data and I fetched that data based on the page that the user went to. I quickly discovered this was a bad idea since I was fetching data left and right and I should be able to just use the data already in the store. So I moved my fetch calls to the App component so that the Activities and Conditions data was retrieved when the app started up.  But then I toiled with how to populate the internal state of a component if the user entered the application on a url that required that the store already be populated in order to render the data.  Enter conditional rendering and the Redirect component! If a user tried to access a page that needed access to the store prior to the store being populated, they were redirected to the home page. 

One of the other things that stumped me was how to handle a controlled form that included checkboxes. They seem like such simple little things, but it turns out that they are pretty complex. I found a GREAT article on building controlled forms for various input types. You can check it out [here]( https://lorenstewart.me/2016/10/31/react-js-forms-controlled-components/). 
This was a huge help!

Lastly, fetch. JavaScript fetch can be such a mystery. It seems like such an easy thing to use, and it sort of is, but there are SO MANY OPTIONS that you can, and sometimes NEED, to include in the call.  I spent 5 hours trying to understand why my Rails API insisted that I wasn’t giving it the hash it needed in the correct format. Turns out I left the headers out of my fetch call (I thought removing factors would make it easier to debug…not so much) and they were necessary for Rails to interpret the data correctly.   

I was pretty surprise that such a small app took me so much time to build but I’m pretty happy with it and very excited to turn it in for review. Feel free to check it out:

* [API](https://github.com/BrownCow371/weather-app-rails-api)
* [Client](https://github.com/BrownCow371/weather-app-rails-api)

