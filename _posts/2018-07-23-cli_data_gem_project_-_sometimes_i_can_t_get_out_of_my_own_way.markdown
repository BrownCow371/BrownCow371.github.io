---
layout: post
title:      "CLI Data Gem Project - sometimes I can’t get out of my own way"
date:       2018-07-23 17:29:07 +0000
permalink:  cli_data_gem_project_-_sometimes_i_can_t_get_out_of_my_own_way
---


### Indecision 
I was a little intimidated by this project, which caused me to procrastinate. I spent a lot of time trying to wrap my head around what the project was all about. I watched the many videos provided on the project page. I attended the Pre Project Study group and went to the Project Office Hours. And then I poured over websites that I might want to use to source my project. I wanted to pull data for something that was unique and that related to my interests. After hours of perusing web pages I could not settle on one idea and ended up submitting proposals for several ideas, hoping that the feedback on the proposals would help launch me out of analysis paralysis/ crippling indecision mode. 

In the end, a phone call to a friend settled my indecision as she suggested a really cool webpage, Stitcher, that she uses to access all of her favorite podcasts. The HTLM was well laid out, the topic seemed novel and I was excited about using it in my project. 

### Sandbox?
So now that I was over the “pick a topic” hurdle, I was ready to start coding….but where?  Opening a new Learn IDE3 session dumped me in my sandbox, which was fine but I could not get my work back after I closed the sandbox.   I could set up a new folder structure in the sandbox and push that up to a github repository, but I could not for the life of me figure out how to get it back down from github once I closed the sandbox…with a little nudge from the Flatiron staff I discovered ‘git clone’…what a wonderful thing!

### Bundler
Armed with my plan and github I started my Stitcher Gem using the `$’bundle gem name_of_new_gem’` process in Bundler which proved very handy. Bundler sets up the basic folder structure for you. But I didn’t understand why it set things up the way that it did…so I spent a long while comparing what was in my new file set to the 50 best restaurants gem while trying to figuring out why things were where they were and what they were used for. 

### JAVASCRIPT!!!
Once I was able to get the file/folder structure sorted out and begin coding I started with my CLI class. I stubbed out methods for the various calls I wanted the user to be able to make and added fake data to my category and show classes so that I could focus on getting the user interface working. Once that was complete I was jazzed up to start working on my scraper class. As I started scraping the Stitcher webpage using Nokogiri I discovered that some of the data I could see in the Inspect window for the webpage wasn’t coming up in my nodeset. I thought I was doing something wrong so I put out a post on the online web development slack channel and a kind colleague pointed out that the page was using javascript to populate the tables/page sections I was trying to pull data from. So Nokogiri could not pull this information. Bummer. Disappointed, I fell back on one of the other proposals that I had submitted (Goodreads best books of 2017) and, starting from scratch, went to town setting up a new github repository, a new gem folder structure and fleshing out a new CLI class running on new fake data. 

### Home Stretch
From here on out the obstacles were much smaller and easier to navigate, even if it took me some time to determine the cause of an issue and come up with a solution. The most prominent of these obstacles were, first, that not all of the books that I was scraping had summaries and second that my application was extremely slow. The summaries issue took me a while to solve because, while using pry, I was getting summary data for the first book that was pulled so I could not understand why I was getting a NoMethodError  - ‘text’ for NilClass….I was getting data...it wasn’t Nil...so why the error? Turns out it just takes one data source to be nil to get said error. So I added some logic to check that the summary existed before trying to grab the text for it. For the slowness issue I added “puts” calls inside my methods to figure out which one was taking the longest. No surprise, the scraping method that collected all of the attributes for each book was a major time hog. And that’s when it dawned on me why the 50 best restaurants gem had reader methods for attributes that scraped the webpage for that data if the data had not already been set. I had thought that was a really odd implementation but after seeing how slow it was to collect all that data up front, it made much more sense to only pull it if you needed it. 

### Closing Thoughts
Once the application was running smoothly I spent some time watching the refactor videos and cleaning up some of my code. I was better about submitting commits during the cleanup phase than I was during the initial creation of the code. I was so caught up in writing the code the first time around that I would forget to push commits often. I’ll need to work on that. But all in all I’m pretty  proud of what I’ve accomplished and I’m excited to submit my project for review! 

