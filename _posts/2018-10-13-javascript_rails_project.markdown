---
layout: post
title:      "JavaScript /Rails Project"
date:       2018-10-13 22:30:18 +0000
permalink:  javascript_rails_project
---



Unlike the Rails Project where I felt like I had a good grasp on what I needed to build to meet the project requirements, the JS project had me stumped. I didn’t know where to begin and didn’t fully understand the requirements that were provided.  This probably had a lot to do with how much I struggled with the JavaScript section starting with the AJAX chapters. The curriculum felt a bit choppy starting at that point and I had a really hard time understanding how all the different pieces and parts were supposed to fit together.  Things cleared up a bit for me after watching the AJAX videos that Avi recorded as well as after going to a few of the AJAX study groups (well worth the time! – thank you, Seth!). 

Since I wasn’t completely clear on how all of the JS project requirements related to my existing Rails project I just wrote them down the best I could in the context of my exiting project and then I started working on the ones that I was clear on in hopes that the others that I was still a bit muddled about would follow.  Oddly, I started with what I thought would be the easiest requirement (finding the next expense for a user and showing it on the Expense Show page) and it turned out to be the most difficult of the tasks I had. But that worked out since it was the requirement I was the most clear on and it paved the way for working out the rest. 

One of the most intimidating aspects of refactoring my Rails project to use a JS front-end was that my front-end includes tables and I was worried about how difficult it would be to create these dynamically with JS. I think Table HTML code is pretty complex as far as HTML goes and I had built a helper in Rails that I was pretty proud of to assist with creating the header and rows in my tables. I was a bit annoyed that I could not reuse this helper code and was a little baffled as to why I needed to rewrite for JS until I realized that if I had built this project from scratch as a Rails back-end/JS front-end app that I would only have had to write it once in JS. And it turns out that building tables in JS is WAY easier than it is in Rails. 

The other major hurdle that I ran into with the JS project was that we were encouraged to use JavaScript instead of JQuery to make our AJAX requests. Initially I got everything working with JQuery and then I refactored the code to use fetch(). Replacing the $.get() requests was pretty straight forward but I floundered a bit with replacing my $.post() request for my new expense form. I was able to finally get it working via some testing in the Console, using console.log() and this resource:  https://davidwalsh.name/fetch

As hoped, the Rails/JS project helped me pull together the concepts from the JS AJAX section that I was previously struggling to wrap my brain around. I feel much more comfortable with the concepts now than I did at the start of the project and I and very glad for that!

